# Open5250 Public Skills Registry 🚀

A curated collection of Claude Code and AI Agent skills designed for **IBM i (AS/400, iSeries)** modernization, RPGLE Free-Format code generation, DDS display files, and green-screen web terminal automation.

Published and distributed for use with **Claude Code**, **LiteLLM Skill Hub**, and **Open5250 AI Pipeline**.

---

## 📦 Available Skills Catalog

| Skill Name | Directory / Path | Category | Description |
| :--- | :--- | :--- | :--- |
| **`ibmi-rpgle-expert`** | [`plugins/ibmi-rpgle`](plugins/ibmi-rpgle/) | Development | IBM i Free-Format RPG IV, embedded SQL (Db2 for i), DDS Physical/Logical files, and display files. |
| **`open5250-sdlc-pipeline`** | [`plugins/open5250-sdlc`](plugins/open5250-sdlc/) | DevOps | 4-Phase SDLC pipeline coordinator (Spec Architect, System Planner, Code Generator, Diagnostic Parser). |
| **`git-pr-workflow`** | [`plugins/git-pr`](plugins/git-pr/) | Productivity | Semantic git commit messages, branch naming conventions, and automated Pull Request summaries. |
| **`sec-audit-advisor`** | [`plugins/sec-audit`](plugins/sec-audit/) | Security | Static code analysis for IBM i: SQL injection detection, hardcoded credentials, and object authority audits. |

---

## ⚡ How to Add to LiteLLM Admin UI

1. Open LiteLLM Admin Dashboard (`/ui/skills/`).
2. Click **`+ Add Skill`**.
3. Use the following parameters:
   - **Repository URL**: `https://github.com/cloudninecura/open5250-skills`
   - **Subfolder path**: `plugins/<skill-folder>` (e.g. `plugins/ibmi-rpgle`)
   - **Skill Name**: `<skill-name>` (e.g. `ibmi-rpgle-expert`)
   - **Domain**: `Enterprise`
   - **Category**: `Development` / `DevOps` / `Security`

---

## 📄 License
Apache-2.0. Open for community and enterprise use.
