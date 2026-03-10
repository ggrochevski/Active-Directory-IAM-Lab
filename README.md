# Active Directory Identity & Access Management Lab

This project simulates an enterprise Identity & Access Management (IAM) environment using **Active Directory Domain Services (AD DS)** as the on-premises identity provider.

The lab demonstrates how authentication, authorization, and access control function inside a Windows enterprise network.

Key identity concepts demonstrated in this environment include:

- Active Directory as an enterprise identity provider
- Kerberos authentication
- Role-Based Access Control (RBAC)
- AGDLP access control model
- NTFS permission management
- Group Policy security controls
- Identity lifecycle simulation

The environment consists of a **Domain Controller running Windows Server 2019** and a **domain-joined Windows 10 client**, connected through a VirtualBox host-only network.

---

# Lab Architecture

| Component | Description |
|----------|-------------|
| Virtualization | Oracle VirtualBox |
| Network | Host-Only Network |
| Domain | treasury.local |
| Domain Controller | DC01 (Windows Server 2019) |
| Client Machine | Windows 10 (Domain Joined) |

The Domain Controller provides:

- Active Directory Domain Services
- DNS
- Authentication services
- Authorization management

---

# Identity Architecture

The lab implements a structured Active Directory environment including:

- Organizational Units
- Security Groups
- User accounts
- Role-based access control

The following sections of the repository explain each component of the identity architecture.

| Section | Description |
|-------|-------------|
| Architecture | Infrastructure and network layout |
| Active Directory | Domain controller setup and directory structure |
| Authentication | Kerberos authentication validation |
| Access Control | RBAC implementation using AGDLP |
| Group Policy | Domain password and security policies |
| Resource Access | File share permissions and authorization testing |

---

# Authentication

Authentication in this environment is handled using **Kerberos**, the default authentication protocol used by Active Directory.

Kerberos tickets were validated using:
