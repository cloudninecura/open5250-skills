---
name: db2i-sql-expert
version: 1.0.0
description: IBM Db2 for i advanced SQL, IBM i Services (QSYS2 views/functions), index advisory, and stored procedures.
author: Open5250 Community
category: Data
keywords:
  - ibm-i
  - db2
  - db2-for-i
  - sql
  - qsys2
  - ibm-i-services
---

# IBM Db2 for i SQL & IBM i Services Skill

Expert guidance on writing optimized SQL queries, DDL, stored procedures, and system queries utilizing IBM i Services (`QSYS2`).

## Standards & Best Practices

1. **IBM i Services (`QSYS2`)**:
   - Query system status: `QSYS2.SYSTEM_STATUS_INFO`.
   - Query active jobs: `QSYS2.ACTIVE_JOB_INFO()`.
   - Query object catalog: `QSYS2.OBJECT_STATISTICS()`.
   - Query user profiles & authorities: `QSYS2.USER_INFO`.

2. **Performance & Indexing**:
   - Use `CREATE INDEX` with `WHERE` clauses (filtered index) and `RCDFMT` for DDS compatibility.
   - Employ `QSYS2.SYSPARTITIONSTAT` to inspect record counts and data sizes.

3. **Stored Procedures & Triggers**:
   - Write modular `SQLRPGLE` or native `SQL` stored procedures using `LANGUAGE SQL` with explicit parameter modes (`IN`, `OUT`, `INOUT`).
