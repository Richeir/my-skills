# powerups

> 个人使用的 Agent Skills 集合 —— 通过结构化引导，帮助你把模糊的想法变成可执行的书面规划。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**语言：** [English](README.md) | [中文](README.zh-CN.md)

## 简介

`powerups` 是一组个人定制的 agent skills。每个 skill 都是一份 `SKILL.md` 指南，告诉 AI 代理在特定场景下如何引导你完成高质量的工作。

**核心原则：不写下来的规划等于没有规划。** 每一步讨论的结论都要落到文档里，而不是停留在对话中。

## 已收录的 Skills

### [`commit-conventions`](./commit-conventions/SKILL.zh-CN.md)

规定每次 git 提交都必须遵循 **Angular / Conventional Commits** 格式：`<type>(<scope>): <subject>`，包含固定的 `type` 集合、小写祈使句英文 subject（≤ 50 字符）以及结构化 body（每行 ≤ 72 字符、`BREAKING CHANGE:` 标注）。

## 使用方式

安装后，当任务命中某个 skill 的触发条件时，代理会自动加载并使用它。

## 安装

本仓库是一个 [pi package](https://pi.dev/packages)，可以用 pi 的包管理器直接安装，无需手动克隆或复制：

```bash
pi install git:github.com/Richeir/powerups
```

当任务命中触发条件时，skill 会被按需加载。`commit-conventions` 会在任何会产生 git 提交的工作中作为项目级约定加载。

> **安全提示：** skill 可以指示模型执行任何操作，使用前请先检查内容。

## 贡献

这是个人使用的 skill 集合，但欢迎提交 Issue 或 PR 分享改进。请遵循仓库内的 `SKILL.md` 编写规范（详见各 skill 的写作说明）。

## 许可证

[MIT](./LICENSE) © 2025 Richeir
