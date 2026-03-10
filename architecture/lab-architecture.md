# Lab Architecture

The lab environment runs on Oracle VirtualBox using a host-only network configuration.

This network allows the virtual machines to communicate internally while remaining isolated from the external network.

Machines in the environment:

Domain Controller

DC01  
Windows Server 2019  
Roles installed:

- Active Directory Domain Services
- DNS Server

IP Address

10.10.10.10

Client Machine

Windows 10  
Domain Joined

The Windows client uses the Domain Controller as its DNS server, enabling Active Directory service discovery and authentication.

This architecture simulates a simplified enterprise identity infrastructure with a centralized identity provider.
