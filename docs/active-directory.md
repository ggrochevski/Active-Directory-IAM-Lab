# Active Directory Configuration

## Active Directory Domain Services

The environment uses Active Directory Domain Services (AD DS) as the enterprise identity provider.

The Domain Controller was successfully promoted and the domain was verified through:

- Active Directory Users and Computers
- domain login functionality
- Kerberos authentication validation

---

## Organizational Unit Structure

The following Organizational Unit structure was created to organize users, groups, and administrative accounts.

```
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
```

This structure reflects common enterprise practices for separating administrative accounts, computers, users, and security groups.

---

## Users Created

Example user accounts were created to simulate employees.

Examples:

```
dkim
jsmith
```

These users were used to simulate identity provisioning and access control scenarios.

---

## Security Groups

Security groups were created to support Role-Based Access Control.

### Global Groups

```
GG_OEE_Employees
GG_OEE_Managers
```

Global groups represent departmental roles.

---

### Domain Local Groups

```
DL_OEE_Share_Read
DL_OEE_Share_Modify
```

Domain Local groups are used to assign permissions to resources.

---

## Identity Lifecycle Simulation

Basic identity lifecycle actions were simulated in the environment.

### Joiner

New users were created and assigned to appropriate security groups.

Example:

```
dkim → GG_OEE_Employees
```

---

### Mover

Group membership changes were performed to simulate changes in access.

Example:

Removing a user from a group revoked access to the resource.

---

### Access Restoration

Re-adding the user to the group restored the user's access.

These tests demonstrated how group membership controls authorization within Active Directory.
