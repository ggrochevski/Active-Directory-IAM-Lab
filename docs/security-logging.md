# Security Logging

## Logging Overview

Security logging was partially implemented in the lab to provide visibility into authentication activity and system processes.

---

## Advanced Audit Policy

Advanced Audit Policy settings were configured to generate security events.

Configured logging includes:

- Logon events
- Process creation events

---

## Event IDs Observed

The following events are generated when auditing is enabled.

```
4624 — Successful logon
4625 — Failed logon
4688 — Process creation
```

These logs help monitor authentication activity and system behavior.

---

## PowerShell Logging

PowerShell logging was also discussed as part of the broader lab work.

PowerShell Script Block Logging generates:

```
Event ID 4104
```

This event records the contents of executed PowerShell commands.

---

## Purpose

Security logging improves visibility into:

- authentication events
- account activity
- process execution
- PowerShell activity

These logs are commonly used for security monitoring and detection.
