# File Share Authorization Testing

A network file share was created on the Domain Controller.

Share path:

\\DC01\oee

Local directory:

C:\TreasuryShares\OEE

NTFS permissions were configured using domain local groups.

Permissions assigned:

DL_OEE_Share_Read → Read  
DL_OEE_Share_Modify → Modify  
Domain Admins → Full Control

Access control was validated from the Windows client.

Testing scenarios included:

Authorized user access  
Unauthorized user access  
Group membership removal revoking access  
Re-adding user restoring access

These tests confirmed that RBAC authorization worked correctly through AGDLP group nesting.
