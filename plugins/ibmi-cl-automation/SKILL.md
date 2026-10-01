---
name: ibmi-cl-automation
version: 1.0.0
description: IBM i Control Language (CL / CLLE) script automation, job queue submission, overrides, and library list management.
author: Open5250 Community
category: Development
keywords:
  - ibm-i
  - cl
  - clle
  - control-language
  - job-control
  - automation
---

# IBM i Control Language (CL / CLLE) Automation Skill

Guides AI models in authoring robust, modern Control Language (CLLE) programs conforming to ILE standards.

## Standards & Best Practices

1. **Structure & Directives**:
   - Start with `PGM` and finish with `ENDPGM`.
   - Use `DCL` for variables with explicit types (`*CHAR`, `*DEC`, `*LGL`).
   - Use `DCLF` for file declarations with Open Feedback monitoring.

2. **Error Handling & Monitoring**:
   - Always include global error trapping using `MONMSG MSGID(CPF0000) EXEC(GOTO CMDLBL(ERROR))`.
   - Forward escape messages properly using `QMHMOVPM` or `SNDPGMMSG MSGTYPE(*ESCAPE)`.

3. **Job & Environment Control**:
   - Manage library lists cleanly: `ADDLIBLE`, `RMVLIBLE`, `CHGLIBL`.
   - Handle database and display overrides: `OVRDBF`, `OVRDSPF`, with proper `DLTOVR`.
   - Use `SBMJOB` with parameterized `JOBQ`, `USER`, and `INLLIBL`.
