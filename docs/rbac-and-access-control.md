# RBAC and Access Control

## Access Model
This lab implements Role-Based Access Control (RBAC) using the AGDLP model:

**Accounts → Global Groups → Domain Local Groups → Permissions**

## Shared Resource
- **Share Path:** `\\DC01\oee`
- **Local Folder:** `C:\TreasuryShares\OEE`

## Group Structure

### Global Groups
- `GG_OEE_Employees`
- `GG_OEE_Managers`

### Domain Local Groups
- `DL_OEE_Share_Read`
- `DL_OEE_Share_Modify`

## Permission Assignment
- `DL_OEE_Share_Read` → Read
- `DL_OEE_Share_Modify` → Modify
- `Domain Admins` → Full Control

Users were not assigned permissions directly.

## Example Authorization Path
```text
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

## Validation Performed
The following tests were completed from the Windows 10 client:

- authorized user successfully accessed the share
- unauthorized user received **Access Denied**
- removing a user from a group revoked access
- re-adding the user restored access

These tests validated group-based authorization behavior.
