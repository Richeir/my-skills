# my-skills

> 个人使用的 Agent Skills 集合 —— 通过结构化引导，帮助你把模糊的想法变成可执行的书面规划。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

**语言：** [English](README.md) | [中文](README.zh-CN.md)

## 简介

`my-skills` 是一组个人定制的 agent skills。每个 skill 都是一份 `SKILL.md` 指南，告诉 AI 代理在特定场景下如何引导你完成高质量的工作。

**核心原则：不写下来的规划等于没有规划。** 每一步讨论的结论都要落到文档里，而不是停留在对话中。

## 已收录的 Skills

### [`project-manager`](./project-manager/SKILL.zh-CN.md)

用于**编程/开发项目**的前期规划。通过 5 阶段的对话式引导，把模糊的编程想法变成结构化、写下来的规划：

| 阶段 | 内容 |
|------|------|
| 1 | 明确目标与验收标准 |
| 2 | 确定技术约束与选型 |
| 3 | 模块与任务拆解（含依赖） |
| 4 | 优先级排序与 MVP 核心路径 |
| 5 | 收敛成一份简洁的 `project-plan.md` |

> 适用场景：开始新开发项目、想法模糊、易遗漏细节、经常返工、想要书面计划再开工。

## 使用方式

安装后，当任务命中某个 skill 的触发条件时，代理会自动加载并使用它。

## 安装

本仓库是一个 [pi package](https://pi.dev/packages)，可以用 pi 的包管理器直接安装，无需手动克隆或复制：

```bash
pi install git:github.com/Richeir/my-skills
```

当任务命中触发条件时，pi 会按需加载 `project-manager` skill。

> **提示：** 如果想手动复制，skill 位于 `project-manager/` 目录，把它放到 `~/.pi/agent/skills/`（或跨运行时别名 `~/.agents/skills/`）下即可。

> **安全提示：** skill 可以指示模型执行任何操作，使用前请先检查内容。

## 贡献

这是个人使用的 skill 集合，但欢迎提交 Issue 或 PR 分享改进。请遵循仓库内的 `SKILL.md` 编写规范（详见各 skill 的写作说明）。

## 许可证

[MIT](./LICENSE) © 2025 Richeir
