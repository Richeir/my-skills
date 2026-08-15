# powerups

> A collection of personal agent skills — guided, structured workflows that turn vague ideas into executable written plans.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Languages:** [English](README.md) | [中文](README.zh-CN.md)

## Introduction

`powerups` is a collection of personal, custom-made agent skills. Each skill is a `SKILL.md` guide that tells an AI agent how to guide you through high-quality work in a specific scenario.

**Core principle: a plan that isn't written down is no plan at all.** Every conclusion from the discussion must land in the document, not stay in the conversation.

## Included Skills

### [`project-manager`](./project-manager/SKILL.md)

Upfront planning for **coding/development projects**. A 5-phase guided conversation turns a vague coding idea into a structured, written plan:

| Phase | Content |
|-------|---------|
| 1 | Clarify goals & acceptance criteria |
| 2 | Settle technical constraints & stack |
| 3 | Module & task breakdown (with dependencies) |
| 4 | Prioritization & MVP core path |
| 5 | Converge into a concise `project-plan.md` |

> Good fits: starting a new dev project, vague ideas, easily missed details, frequent rework, or wanting a written plan before starting.

## Usage

Once installed, the agent automatically loads and uses a skill when a task matches its trigger conditions. Each agent looks for skills in its own directory (see below).

## Installation

This repo is a [pi package](https://pi.dev/packages), so you can install it directly with pi's package manager — no manual cloning or copying:

```bash
pi install git:github.com/Richeir/powerups
```

Pi loads the `project-manager` skill on demand when a task matches its trigger conditions.

> **Note:** If you prefer to copy manually, the skill lives in the `project-manager/` directory; place it under `~/.pi/agent/skills/` (or the cross-runtime alias `~/.agents/skills/`).

> **Security:** skills can instruct the model to perform any action. Review the content before use.

## Contributing

This is a personal skill collection, but Issues and PRs sharing improvements are welcome. Please follow the `SKILL.md` authoring conventions used in this repo.

## License

[MIT](./LICENSE) © 2025 Richeir
