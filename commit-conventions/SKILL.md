---
name: commit-conventions
description: Use when working in a project that produces git commits, to enforce consistent, well-formed commit messages across every commit you create.
---

# Commit Conventions

## Overview

Every git commit must follow the **Angular / Conventional Commits** format. A commit message that doesn't match the template is a failed commit message.

## When to Use

- Writing or rewriting any commit message
- Reviewing commit messages before pushing
- Creating a commit on behalf of the user
- Scope runs across all projects, no exceptions

## Quick Reference

```
<type>(<scope>): <subject>

<body>
```

| part | rule |
|------|------|
| `type` | lowercase; one of the table below (required) |
| `scope` | optional; lowercase, wrapped in `()` |
| `subject` | English, imperative, lowercase start, no trailing `.`, ≤ 50 chars |
| `body` | blank line after subject; each line ≤ 72 chars; `BREAKING CHANGE:` marks breaking changes |

### Types

| type | use for |
|------|---------|
| `feat` | new feature / file |
| `fix` | bug fix |
| `docs` | documentation only |
| `refactor` | refactor without behavior change |
| `chore` | misc (deps, config, build) |
| `style` | formatting only, no logic change |
| `perf` | performance optimization |
| `test` | tests |
| `build` | build system / external deps |
| `ci` | CI config |

## Example

```text
feat(demo): add forecast query

demo.py now logs in and queries representative APIs per category,
printing real return values (error_code/fields/data).
```

## Common Mistakes

- Uppercase type (`Feat:`) — type must be lowercase
- Capitalized subject ("Add ...") — subject starts lowercase
- Trailing period on subject — subject ends with no `.`
- Pasting the whole diff as the message — summarize intent, not changes
- Skipping body background when it's needed — use a blank line, ≤ 72 chars per line
