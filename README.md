# powerups

> A collection of personal agent skills — guided, structured workflows that turn vague ideas into executable written plans.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**Languages:** [English](README.md) | [中文](README.zh-CN.md)

## Introduction

`powerups` is a collection of personal, custom-made agent skills. Each skill is a `SKILL.md` guide that tells an AI agent how to guide you through high-quality work in a specific scenario.

**Core principle: a plan that isn't written down is no plan at all.** Every conclusion from the discussion must land in the document, not stay in the conversation.

## Included Skills

### [`commit-conventions`](./commit-conventions/SKILL.md)

Enforces the **Angular / Conventional Commits** format on every git commit: `<type>(<scope>): <subject>` with a defined `type` set, lowercase imperative English subjects (≤ 50 chars), and structured bodies (≤ 72 chars, `BREAKING CHANGE:` markers).

## Usage

Once installed, the agent automatically loads and uses a skill when a task matches its trigger conditions. Each agent looks for skills in its own directory (see below).

## Installation

This repo is a [pi package](https://pi.dev/packages), so you can install it directly with pi's package manager — no manual cloning or copying:

```bash
pi install git:github.com/Richeir/powerups
```

Skills are loaded on demand when a task matches their trigger conditions. `commit-conventions` loads as a project-level convention whenever work produces a git commit.

> **Security:** skills can instruct the model to perform any action. Review the content before use.

## Contributing

This is a personal skill collection, but Issues and PRs sharing improvements are welcome. Please follow the `SKILL.md` authoring conventions used in this repo.

## License

[MIT](./LICENSE) © 2025 Richeir
