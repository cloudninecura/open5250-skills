---
name: open5250-sdlc-pipeline
version: 1.0.0
description: Open5250 4-phase SDLC code generation and diagnostic parsing pipeline coordinator.
author: Open5250 Community
category: DevOps
keywords:
  - open5250
  - sdlc
  - build-pipeline
  - code-generator
  - diagnostics
---

# Open5250 SDLC Pipeline Skill

Orchestrates the 4-phase SDLC lifecycle for transforming functional specifications into compiled IBM i programs.

## 4 Pipeline Phases

1. **Phase 1: Spec Architect (`spec-architect`)**:
   - Parses business requirements into structured object inventories (`PF`, `LF`, `DSPF`, `RPGLE`, `CLLE`).
   - Identifies dependencies, primary keys, relationships, and screen layouts.

2. **Phase 2: System Planner (`system-planner`)**:
   - Constructs directed acyclic build graphs (DAGs).
   - Generates deterministic compile sequences (e.g. `PF -> LF -> DSPF -> RPGLE -> CLLE`).

3. **Phase 3: Code Generator (`code-generator`)**:
   - Synthesizes 100% compliant source members for each planned object in the build sequence.
   - Employs modular templates and ensures column alignment for DDS.

4. **Phase 4: Diagnostic Parser (`diagnostic-parser`)**:
   - Parses compiler listing outputs (`EVFEVENT` / spool files).
   - Identifies syntax errors (e.g., `RNF7030`, `RNF5347`, `CPD0104`), isolates exact source lines, and outputs actionable fix diffs.
