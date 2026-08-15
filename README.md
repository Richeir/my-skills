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

Once installed, the agent automatically loads and uses a skill when a task matches its trigger conditions. Each agent looks for skills in its own directory (see below).

## Installation

Clone the repo, then copy the skill into the directory for your agent runtime:

```bash
git clone git@github.com:Richeir/my-skills.git
cd my-skills
```

### Claude Code

```bash
mkdir -p ~/.claude/skills
cp -r project-manager ~/.claude/skills/
```

### Codex (OpenAI)

```bash
mkdir -p ~/.codex/skills
cp -r project-manager ~/.codex/skills/
# or the cross-runtime alias:
mkdir -p ~/.agents/skills
cp -r project-manager ~/.agents/skills/
```

### pi

```bash
mkdir -p ~/.pi/agent/skills
cp -r project-manager ~/.pi/agent/skills/
# or the cross-runtime alias:
mkdir -p ~/.agents/skills
cp -r project-manager ~/.agents/skills/
```

> **Note:** `~/.agents/skills/` is a cross-runtime alias recognized by several harnesses. To install for multiple agents at once, just copy the skill there once.

> **Security:** skills can instruct the model to perform any action. Review the content before use.

## Contributing

This is a personal skill collection, but Issues and PRs sharing improvements are welcome. Please follow the `SKILL.md` authoring conventions used in this repo.

## License

[MIT](./LICENSE) © 2025 Richeir
