---
name: pre-commit-checklist
description: Use when about to commit code or mark a task complete, to run the required verification checks before declaring it done.
---

# Pre-Commit Checklist

## Overview

Before committing or declaring a task complete, run the checks below. A change that doesn't pass them is not done.

## When to Use

- Just before creating a commit
- Before claiming a task/feature is complete
- After finishing an implementation

## Checklist

- [ ] **Build passes** — build command exits 0 (e.g. `npm run build`)
- [ ] **Tests pass** — unit and e2e tests all green (`npm test`)
- [ ] **Lint passes** — lint runs with no errors (`npm run lint`)
- [ ] **No debug leftovers** — no stray `console.log`, `debugger`, or commented-out code
- [ ] **No secrets committed** — no API keys, tokens, or `.env` values in the diff
- [ ] **Only intended files staged** — no stray/generated artifacts
- [ ] **Commit message follows format** — see the `commit-conventions` skill (Angular/Conventional Commits)

If any box is unchecked, fix it before committing. Verification is evidence, not assertion — run the commands and confirm their actual output.

## Common Mistakes

- "I think it builds" without actually running it
- Leaving debug logging "for now"
- Committing secrets from `.env` or hardcoded values
