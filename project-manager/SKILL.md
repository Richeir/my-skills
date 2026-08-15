---
name: project-manager
description: Use when starting a new coding/development project and needing to plan it before writing code — when the idea is vague, when details are easily missed and cause rework, or when you want a written plan before coding.
---

# Project Manager

> **Languages:** [English](SKILL.md) | [中文](SKILL.zh-CN.md)

## Overview

Turns a vague coding idea into a **structured, written-down** plan: first clarify goals and acceptance criteria, then settle the technical approach, break the work into executable tasks, prioritize with a clear MVP core path, and finally converge on a concise `project-plan.md`.

**Core principle: a plan that isn't written down is no plan at all.** Every conclusion from the discussion must land in the document, not stay in the conversation.

## When to Use

Use for one-time **upfront planning before writing code**. Good fits:
- Starting a brand-new development project
- The idea is still vague and you don't know where to start
- Details are easily missed and rework is common
- You want a written plan before starting

**Do not use** for mid-development progress tracking or on code that's already written.

## Core Pattern: 5-Phase Guided Conversation

Walk through the 5 phases in order. In each phase, use questions to make the other party say their thinking out loud, **and record/confirm the conclusion** rather than leaving it in their head. Don't jump to the next phase before finishing the current one.

| # | Phase | Questions to resolve |
|---|-------|----------------------|
| 1 | Goals & acceptance criteria | What does success look like? Core requirements? What "must be able to…"? |
| 2 | Technical constraints & stack | Existing tech stack? Platform/environment constraints? Language/framework preference? Need persistence/network/third-party deps? |
| 3 | Module & task breakdown | Which modules? Which executable tasks per module? Dependencies between tasks? |
| 4 | Prioritization & MVP | Which path is core and must-do? What can be postponed? What can be cut? |
| 5 | Converge into a document | Assemble phases 1-4 into `project-plan.md`. |

**Questioning tips**:
- Ask one key question at a time; wait for the answer before the next.
- When something is vague or undefined (e.g. "handle all errors"), ask for the concrete scope.
- After each phase, restate the conclusion in a line or two to confirm before moving on.

## Quick Reference (Output Structure)

Generate a concise `project-plan.md` that fits on one screen:

```markdown
# <Project Name>
## Goals & Acceptance Criteria
- what success looks like
- core requirements
## Technical Approach
- stack / constraints / module layout / data flow
## Task List
- [ ] task one (priority: P0 | depends on: none) one task per line
- [ ] task two (priority: P1 | depends on: task one)
## Prioritization & MVP Core Path
- must-do (core path) / can postpone / can cut
```

One **task per line**, each tagged with priority and dependencies. Save the file at the project root by default, or ask where to put it.

## Common Mistakes

| Mistake | Fix |
|---------|-----|
| Listing features and starting right away, no acceptance criteria | Do phase 1 first; define what "done" looks like |
| Assuming a tech stack without asking about constraints | Must confirm in phase 2 |
| Tasks without dependencies | Tag each task's dependencies in phase 3 |
| Mixing all requirements together, no priorities | In phase 4, separate MVP core path from cuttable items |
| Ending the discussion without a document | Phase 5 must produce `project-plan.md` |
| Asking many questions at once | Ask one at a time |

## Red Flags — Signals You've Gone Off Track

- Listing features with no acceptance criteria
- Skipping technical constraints and just assuming a solution
- Task list without priorities or dependencies
- Conversation ends with no `project-plan.md`
- "I'll keep it in my head and write it down later"

**If any of these appear = stop and go back to the corresponding phase to fill the gap.**
