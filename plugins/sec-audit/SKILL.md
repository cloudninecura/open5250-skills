---
name: sec-audit-advisor
version: 1.0.0
description: Static code analysis for IBM i applications - detects SQL injection, hardcoded credentials, and insecure object authority profiles.
author: Open5250 Community
category: Security
keywords:
  - security
  - sast
  - audit
  - ibm-i-security
  - compliance
---

# Security & Static Audit Advisor Skill

Analyzes DDS, RPGLE, and CL source files to uncover vulnerability patterns and privilege escalation risks.

## Audit Checks

1. **SQL Injection**:
   - Flags dynamic SQL strings constructed via concatenation (`'SELECT * FROM ' + tableName`) without parameter markers (`?` or `:var`).
2. **Hardcoded Passwords & Secrets**:
   - Detects hardcoded passwords in CL commands (`CHGUSRPRF PASSWORD(...)`, `SNDNETSPLF ... PASSWORD(...)`).
3. **Adopted Authority & Special Rights**:
   - Warns on programs compiling with `USRPRF(*OWNER)` and `AUT(*ALL)` owned by high-privilege profiles (`QSECOFR`).
