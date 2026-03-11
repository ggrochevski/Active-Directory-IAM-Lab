# Kerberos Authentication Validation

## Authentication Protocol

Active Directory uses Kerberos as its default authentication protocol.

Kerberos allows secure authentication without repeatedly transmitting user credentials across the network.

---

## Kerberos Validation Method

Authentication was validated on the Windows client using:

```powershell
klist
```

This command displays the Kerberos tickets currently held by the logged-in user.

---

## Ticket Granting Ticket (TGT)

After logging in, the following ticket was observed:

```
krbtgt/TREASURY.LOCAL
```

This represents the Ticket Granting Ticket issued by the Domain Controller.

The TGT allows the user to request service tickets for accessing network resources.

---

## Service Ticket

After accessing the file share, an additional ticket appeared:

```
cifs/DC01
```

This ticket was issued for the SMB service hosted on the Domain Controller.

---

## Authentication Flow

The authentication process follows this sequence:

```
User logs into workstation
↓
Domain Controller validates credentials
↓
Ticket Granting Ticket issued
↓
User requests service ticket
↓
Service ticket issued
↓
User accesses network resource
```

---

## Resource Access Example

Example resource accessed during validation:

```
\\DC01\oee
```

Access to the resource required both:

- successful Kerberos authentication
- proper group-based authorization

This confirmed that Kerberos authentication was functioning correctly within the domain.
