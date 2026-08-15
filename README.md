# my-skills

> A collection of personal agent skills — guided, structured workflows that turn vague ideas into executable written plans.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Languages:** [English](README.md) | [中文](README.zh-CN.md)

## Introduction

`my-skills` is a collection of personal, custom-made agent skills. Each skill is a `SKILL.md` guide that tells an AI agent how to guide you through high-quality work in a specific scenario.

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

Point your agent's skills search path at this repo (or the individual skill directory you need). Common locations:

- `~/.claude/skills/`
- `~/.agents/skills/`
- or a custom directory configured by your agent runtime

Once configured, the agent automatically loads and uses a skill when a task matches its trigger conditions.

## Installation

```bash
git clone git@github.com:Richeir/my-skills.git
# copy the skill directory you need into your skills path
cp -r my-skills/project-manager ~/.claude/skills/
```

## Contributing

This is a personal skill collection, but Issues and PRs sharing improvements are welcome. Please follow the `SKILL.md` authoring conventions used in this repo.

## License

[MIT](./LICENSE) © 2025 Richeir
