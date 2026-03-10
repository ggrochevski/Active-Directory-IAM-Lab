# Active Directory Configuration

## Domain Services
The lab uses Active Directory Domain Services (AD DS) as the on-premises identity provider.

The Domain Controller was successfully promoted and the domain structure was validated through:
- Active Directory Users and Computers
- successful domain logon
- Kerberos authentication behavior

## Organizational Units
```text
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

## Example Users
- `dkim`
- `jsmith`

These users were used to simulate employee identities in departmental structures.

## Security Groups

### Global Groups
- `GG_OEE_Employees`
- `GG_OEE_Managers`

### Domain Local Groups
- `DL_OEE_Share_Read`
- `DL_OEE_Share_Modify`

## Identity Lifecycle Simulation

### Joiner
- New users were created
- Users were assigned to department-aligned groups

### Mover
- Group membership changes were made to simulate access changes

### Access Revocation / Restoration
- Removing a user from a security group revoked access
- Re-adding the user restored access

This simulated basic identity provisioning and deprovisioning workflows.
