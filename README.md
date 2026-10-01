# Open5250 Public Skills Registry 🚀

A curated collection of Claude Code and AI Agent skills designed for **IBM i (AS/400, iSeries)** modernization, RPGLE Free-Format code generation, DDS display files, Control Language scripts, Db2 for i queries, and green-screen web terminal automation.

Published and distributed for use with **Claude Code**, **LiteLLM Skill Hub**, and **Open5250 AI Pipeline**.

---

## 📦 Complete Skills Catalog

| Skill Name | Path in Repository | Category | Core Capabilities |
| :--- | :--- | :--- | :--- |
| **`ibmi-rpgle-expert`** | [`plugins/ibmi-rpgle`](plugins/ibmi-rpgle/) | Development | Free-Format RPG IV (`**FREE`), embedded SQL, DDS physical and subfile display files. |
| **`ibmi-cl-automation`** | [`plugins/ibmi-cl-automation`](plugins/ibmi-cl-automation/) | Development | Control Language (CL/CLLE) scripts, error trapping (`MONMSG`), library lists (`CHGLIBL`), and `SBMJOB`. |
| **`db2i-sql-expert`** | [`plugins/db2i-sql`](plugins/db2i-sql/) | Data | Advanced Db2 for i SQL, IBM i Services (`QSYS2.*`), stored procedures, and index optimization. |
| **`open5250-sdlc-pipeline`** | [`plugins/open5250-sdlc`](plugins/open5250-sdlc/) | DevOps | 4-Phase SDLC coordinator (Spec Architect, System Planner, Code Generator, Diagnostic Parser). |
| **`playwright-5250-testing`** | [`plugins/playwright-5250`](plugins/playwright-5250/) | Testing | Automated E2E testing for Open5250 terminal grids, cursor tracking, and function key assertions. |
| **`git-pr-workflow`** | [`plugins/git-pr`](plugins/git-pr/) | Productivity | Semantic git commit messages, branch naming conventions, and automated Pull Request summaries. |
| **`sec-audit-advisor`** | [`plugins/sec-audit`](plugins/sec-audit/) | Security | Static analysis for IBM i: SQL injection detection, secret leaks, and adopted authority audits. |

---

## ⚡ How to Add to LiteLLM Admin UI

1. Open LiteLLM Admin Dashboard (`/ui/skills/`).
2. Click **`+ Add Skill`**.
3. Use the following parameters:
   - **Repository URL**: `https://github.com/cloudninecura/open5250-skills`
   - **Subfolder path**: `plugins/<skill-folder>` (e.g. `plugins/ibmi-rpgle`)
   - **Skill Name**: `<skill-name>` (e.g. `ibmi-rpgle-expert`)
   - **Category**: `Development` / `Data` / `DevOps` / `Testing` / `Security`

---

## 📄 License
Apache-2.0. Open for community and enterprise use.
