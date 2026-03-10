# Kerberos Validation

## Authentication Protocol
The lab uses Kerberos as the default authentication protocol for Active Directory.

## Validation Method
Kerberos tickets were inspected on the Windows 10 client using:

```powershell
klist
```

## Tickets Observed

### Ticket Granting Ticket (TGT)
```text
krbtgt/TREASURY.LOCAL
```

This confirmed that the user successfully authenticated to the domain and received a Ticket Granting Ticket.

### Service Ticket
```text
cifs/DC01
```

This ticket appeared after accessing the SMB file share on the Domain Controller.

It confirmed that:
- the client requested a service ticket
- Kerberos was used for SMB authentication
- access to the network resource was authenticated through Active Directory

## Authentication Flow
```text
User logs into workstation
↓
Domain Controller validates credentials
↓
TGT issued
↓
User requests service ticket
↓
CIFS ticket issued
↓
User accesses \\DC01\oee
```
