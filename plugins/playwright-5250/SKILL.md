---
name: playwright-5250-testing
version: 1.0.0
description: End-to-end automated testing patterns for Open5250 web terminal grids, keyboard inputs, function keys, and field validation.
author: Open5250 Community
category: Testing
keywords:
  - playwright
  - e2e
  - testing
  - open5250
  - automation
  - web-terminal
---

# Playwright Open5250 Terminal Testing Skill

Guides AI models and engineers in authoring reliable Playwright E2E tests against Open5250 terminal interfaces.

## Standards & Best Practices

1. **Terminal Grid Targeting**:
   - Locate character cells using row/column data attributes: `[data-row="X"][data-col="Y"]`.
   - Wait for terminal readiness: `page.waitForSelector('.terminal-grid')`.

2. **Keyboard & Function Key Emulation**:
   - Send Enter / Field Exit: `page.keyboard.press('Enter')`.
   - Send Function keys: `page.keyboard.press('F3')`, `page.keyboard.press('F12')`, `page.keyboard.press('PageDown')`.

3. **Screen Text Assertions**:
   - Match exact green-screen screen areas: verify menu titles (`MAIN`), user prompt inputs (`User . . . . . .`), and error lines (row 24).
