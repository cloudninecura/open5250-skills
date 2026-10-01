---
name: ibmi-rpgle-expert
version: 1.0.0
description: IBM i RPGLE Free-Format code generator, DDS display/printer file parser, and Db2 for i embedded SQL modernization expert.
author: Open5250 Community
category: Development
keywords:
  - ibm-i
  - rpgle
  - dds
  - db2
  - as400
  - free-format
---

# IBM i & RPGLE Modernization Skill

This skill guides AI models and developer tooling in generating production-grade, modular, modern IBM i source code conforming strictly to IBM i 7.3+ standards.

## Rules & Coding Standards

1. **Fully Free-Format RPG IV (`**FREE`)**:
   - Always start RPGLE source files with `**FREE` on line 1 column 1.
   - Never generate fixed-format column-based RPG specifications unless explicitly requested for legacy maintenance.
   - Use `dcl-f`, `dcl-s`, `dcl-ds`, `dcl-pr`, `dcl-pi`, and `dcl-proc`.

2. **DDS Display Files (`DSPF`) & Physical Files (`PF`)**:
   - Adhere strictly to 80-character fixed DDS column format (`A` in column 6).
   - Use standard record format names (e.g., `HEADER`, `CUSTSFL`, `CUSTCTL`, `FOOTER`).
   - Include function key assignments (`CF03(03 'Exit')`, `CF12(12 'Cancel')`, `PAGEDOWN(25)`).

3. **Embedded SQL (Db2 for i)**:
   - Use `exec sql` blocks with proper `SQLCODE` / `SQLSTATE` error checking.
   - Parameterize all inputs with host variables (`:variableName`) to prevent SQL injection.
   - Prefer `FETCH FIRST n ROWS ONLY` and cursor-based batching for subfile loading.
