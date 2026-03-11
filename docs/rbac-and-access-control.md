# RBAC and Access Control

## Authorization Model

The environment implements Role-Based Access Control using Microsoft's recommended AGDLP model.

```
Accounts → Global Groups → Domain Local Groups → Permissions
```

This model separates user identities from resource permissions.

---

## Shared Resource

The following network share was created:

```
\\DC01\oee
```

Local path:

```
C:\TreasuryShares\OEE
```

---

## Group Structure

### Global Groups

```
GG_OEE_Employees
GG_OEE_Managers
```

Global groups represent user roles or departments.

---

### Domain Local Groups

```
DL_OEE_Share_Read
DL_OEE_Share_Modify
```

Domain Local groups receive permissions on the resource.

---

## NTFS Permissions

Permissions assigned to the folder:

```
DL_OEE_Share_Read → Read
DL_OEE_Share_Modify → Modify
Domain Admins → Full Control
```

Users were not assigned permissions directly.

---

## Example Authorization Path

```
dkim
↓
GG_OEE_Employees
↓
DL_OEE_Share_Modify
↓
NTFS Permission
↓
\\DC01\oee
```

---

## Authorization Validation

Access control behavior was tested from the domain-joined client.

Tests performed:

- authorized user accessed the share successfully
- unauthorized user received Access Denied
- removing the user from the group revoked access
- re-adding the user restored access

These tests confirmed that authorization was correctly enforced through group membership.
