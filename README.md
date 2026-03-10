Active Directory Identity & Access Management Lab
Project Overview

This project simulates an enterprise Identity & Access Management (IAM) environment using Active Directory Domain Services as the on-prem identity provider.

The lab demonstrates core identity infrastructure concepts used in enterprise Windows environments, including authentication using Kerberos, authorization using Role-Based Access Control (RBAC), and resource access management using NTFS permissions.

The environment consists of a Windows Server domain controller running Active Directory Domain Services and DNS, along with a domain-joined Windows client used to simulate enterprise user authentication.

Lab Architecture

Virtualization platform:

Oracle VirtualBox

Network configuration:

Host-Only Adapter

Machines in the lab:

Domain Controller

Server Name: DC01
Operating System: Windows Server 2019
Roles Installed:

Active Directory Domain Services

DNS Server

IP Address:

10.10.10.10

Client Machine

Operating System: Windows 10

Configuration:

Domain Joined to:

treasury.local

The client machine uses the Domain Controller as its DNS server to enable Active Directory service discovery and authentication.

Identity Infrastructure

The Active Directory domain deployed in the lab is:

treasury.local

Active Directory serves as the identity provider for the environment, responsible for authentication, authorization, and directory services.

The Domain Controller provides:

Kerberos authentication

LDAP directory services

DNS service discovery

Organizational Unit Structure

The following OU structure was implemented to simulate enterprise identity organization.

treasury.local
│
├── Corp-Admins
├── Corp-Computers
├── Corp-Groups
│   ├── Distribution
│   └── Security
│
└── Corp-Users
    ├── OEE
    ├── IT
    ├── ABCC
    ├── MSRB

This structure separates administrative accounts, users, computers, and security groups.

Authentication Mechanism

Authentication in the environment uses Kerberos, the default authentication protocol for Active Directory.

Authentication flow:

User login
↓
Domain Controller validates credentials
↓
Kerberos Ticket Granting Ticket (TGT) issued
↓
Client requests service ticket
↓
Service ticket issued
↓
Access to network resource

Kerberos tickets were validated using the command:

klist

Example tickets observed:

krbtgt/TREASURY.LOCAL
cifs/DC01

The CIFS ticket appeared after accessing the network file share hosted on the Domain Controller.

Role-Based Access Control (RBAC)

Authorization in the lab was implemented using Microsoft's AGDLP model.

Structure:

Accounts
↓
Global Groups
↓
Domain Local Groups
↓
Permissions

Example implementation:

User: dkim
↓
GG_OEE_Employees
↓
DL_OEE_Share_Modify
↓
NTFS Permission
↓
Access to \\DC01\oee

Users are never assigned permissions directly.

Access is managed through group membership.

Resource Access Implementation

A file share was created on the Domain Controller.

Share:

\\DC01\oee

Local path:

C:\TreasuryShares\OEE

NTFS permissions were configured using Domain Local Groups.

DL_OEE_Share_Read → Read
DL_OEE_Share_Modify → Modify
Domain Admins → Full Control

Access control testing confirmed that authorization behaved as expected.

Tests performed:

Authorized users successfully accessed the share

Unauthorized users received access denied

Removing users from groups revoked access

Re-adding users restored access

This validated RBAC enforcement through group membership.

Group Policy Security Controls

Domain security policies were configured through the Default Domain Policy.

Policies implemented included:

Password Policy

Minimum password length

Password complexity requirements

Password expiration

Account Lockout Policy

Lockout threshold

Lockout duration

Reset counter time

These policies enforce baseline domain security standards.

Security Logging

Audit logging was partially configured.

The following logging was enabled:

Advanced Audit Policy:

Logon events

Process creation (Event ID 4688)

PowerShell logging concepts were also introduced, including Script Block Logging (Event ID 4104).
