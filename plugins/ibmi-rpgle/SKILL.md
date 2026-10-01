---
name: ibmi-rpgle-expert
version: 1.1.0
description: Comprehensive IBM i system architecture, object hierarchy (*LIB, *FILE, *PGM, *SRVPGM, *MODULE, *CMD, *DTAARA, *DTAQ, *JRN, *MSGQ), Free-Format RPG IV (**FREE), DDS, and Db2 for i modernization expert.
author: Open5250 Community
category: Development
keywords:
  - ibm-i
  - as400
  - iseries
  - os400
  - rpgle
  - sqlrpgle
  - free-format
  - dds
  - db2-for-i
  - qsys
  - object-hierarchy
  - "*LIB"
  - "*FILE"
  - "*PGM"
  - "*SRVPGM"
  - "*MODULE"
  - "*CMD"
  - "*DTAARA"
  - "*DTAQ"
  - "*MSGF"
  - "*MSGQ"
  - "*JRN"
  - "*JRNRCV"
  - "*BNDDIR"
  - "*BNDSRVPGM"
  - "*USRPRF"
  - "*JOBD"
  - "*JOBQ"
  - "*OUTQ"
  - "*CLS"
  - "*SBSD"
  - "*TBL"
  - "*MENU"
  - "*PNLGRP"
  - "*USRIDX"
  - "*USRQ"
  - "*USRSPO"
  - PF
  - LF
  - DSPF
  - PRTF
  - SAVF
  - ICF
  - DDM
---

# IBM i & RPGLE Modernization Expert Skill

Comprehensive knowledge of the IBM i single-level storage architecture, QSYS object hierarchy, ILE compilation pipeline, and modern Free-Format RPG IV (`**FREE`).

---

## 1. IBM i Object Hierarchy & Storage Architecture

IBM i organizes all entities under an object-based encapsulation model rooted in library `QSYS`:

### Hierarchy:
```
QSYS (*LIB - Root system library)
  ├── QSYS2 (*LIB - SQL catalogs & IBM i Services views)
  ├── QGPL (*LIB - General Purpose Library)
  ├── QTEMP (*LIB - Temporary per-job library, dynamic lifecycle)
  └── USERLIB (*LIB - User applications & data)
        ├── QDDSSRC  (*FILE / *PF-SRC - DDS source physical file)
        ├── QRPGLESRC (*FILE / *PF-SRC - RPGLE source physical file)
        ├── QCLLESRC  (*FILE / *PF-SRC - CLLE source physical file)
        ├── QCBLLESRC (*FILE / *PF-SRC - COBOL source physical file)
        ├── QSQLSRC   (*FILE / *PF-SRC - DDL & SQL source physical file)
        │
        ├── Database Objects:
        │     ├── *FILE (*PF - Physical File / SQL Table)
        │     ├── *FILE (*LF - Logical File / SQL View / Index)
        │     ├── *JRNRCV (Journal Receiver)
        │     └── *JRN (Journal definition attaching *FILE / *LIB)
        │
        ├── UI & Device Files:
        │     ├── *FILE (*DSPF - 5250 Display File for Workstations)
        │     ├── *FILE (*PRTF - Spool/Printer File definition)
        │     ├── *FILE (*SAVF - Save File backup stream)
        │     └── *FILE (*ICFF - Inter-system Communications Function)
        │
        ├── Executable & ILE Components:
        │     ├── *MODULE (Compiled single compilation unit: CRTRPGMOD / CRTCLMOD)
        │     ├── *SRVPGM (Service Program shared library: CRTSRVPGM, export binder source)
        │     ├── *BNDDIR (Binding Directory linking modules & service programs)
        │     ├── *PGM (ILE Program executable: CRTPGM / CRTBNDRPG)
        │     └── *CMD (Custom Command Definition: CRTCMD linked to *PGM)
        │
        ├── Inter-Process Communication & Data Stores:
        │     ├── *DTAARA (Data Area - small shared state storage, *LDA per-job)
        │     ├── *DTAQ (Data Queue - FIFO/LIFO/Keyed fast async messaging)
        │     ├── *USRIDX (User Index - high-performance key-value index)
        │     ├── *USRQ (User Queue - memory-mapped direct queue)
        │     └── *USRSPO (User Space - raw memory block storage)
        │
        ├── Messages & Help:
        │     ├── *MSGF (Message File containing predefined CPF/RNF/USER messages)
        │     ├── *MSGQ (Message Queue: QSYSOPR, user message queues)
        │     └── *PNLGRP (Panel Group for UIM help text & dynamic menus)
        │
        └── Work Management & Security:
              ├── *USRPRF (User Profile & authority credentials)
              ├── *JOBD (Job Description: defaults for libraries, queues, priority)
              ├── *JOBQ (Job Queue: routing jobs to batch subsystems)
              ├── *OUTQ (Output Queue: spool files)
              ├── *SBSD (Subsystem Description: QINTER, QBATCH, QSYSWRK)
              └── *CLS (Class: run priority, time slice, max CPU)
```

---

## 2. Library List Resolution Order (*LIBL)

System commands and program calls resolve unqualified object names (`MYPGM`, `CUSTOMER`) using the thread's `*LIBL`:

1. **System Part (`*SYSLIBL`)**: `QSYS`, `QSYS2`, `QHLPSYS`, `QUSRSYS`
2. **Product Part (`*PRDLIBL`)**: Added automatically by active menus or licensed programs
3. **Current Library (`*CURLIB`)**: Working user library (or `*CRTDFT`)
4. **User Part (`*USRLIBL`)**: Application libraries ordered by dependency (e.g., `APPDATA`, `APPDEV`, `QGPL`, `QTEMP`)

---

## 3. ILE Compilation & Modernization Pipeline

1. **Deterministic Build Sequence**:
   - `Physical Files (*FILE PF / DDL)` ➔ `Logical Files (*FILE LF / Indexes)` ➔ `Display Files (*FILE DSPF)` ➔ `Modules (*MODULE)` ➔ `Service Programs (*SRVPGM)` ➔ `Binding Directories (*BNDDIR)` ➔ `Programs (*PGM)` ➔ `Commands (*CMD)`
2. **Fully Free-Format RPG IV (`**FREE`)**:
   - Always start RPGLE source files with `**FREE` on line 1, column 1.
   - Declare files: `dcl-f CUSTOMER disk(*ext) usage(*input:*output) keyed;`
   - Declare display: `dcl-f CUSTDSP workstn indds(wsInd);`
   - Modular procedures: `dcl-proc GetCustomer export; ... dcl-pi; ... end-proc;`
3. **Embedded SQL (Db2 for i)**:
   - Parameterized statements using host variables (`:custNo`).
   - Clean cursor management with `open`, `fetch`, `close`.
   - Error verification testing `SQLCODE = 0` or checking `SQLSTATE`.
4. **DDS Display Formatting**:
   - Exact 80-column alignment with `A` in column 6.
   - Screen record formats with indicator data structures (`INDDS`).
