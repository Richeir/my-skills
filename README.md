# my-skills

> 个人使用的 Agent Skills 集合 —— 通过结构化引导，帮助你把模糊的想法变成可执行的书面规划。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

## 简介

`my-skills` 是一组个人定制的 agent skills。每个 skill 都是一份 `SKILL.md` 指南，告诉 AI 代理在特定场景下如何引导你完成高质量的工作。

**核心原则：不写下来的规划等于没有规划。** 每一步讨论的结论都要落到文档里，而不是停留在对话中。

## 已收录的 Skills

### [`project-manager`](./project-manager/SKILL.md)

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

将本仓库（或你需要的单个 skill 目录）配置到你的 agent 的 skills 搜索路径即可。常见路径：

- `~/.claude/skills/`
- `~/.agents/skills/`
- 或由你的 agent 运行时指定的自定义目录

配置后，当任务命中某个 skill 的触发条件时，代理会自动加载并使用它。

## 安装

```bash
git clone git@github.com:Richeir/my-skills.git
# 将需要的 skill 目录复制到你的 skills 路径
cp -r my-skills/project-manager ~/.claude/skills/
```

## 贡献

这是个人使用的 skill 集合，但欢迎提交 Issue 或 PR 分享改进。请遵循仓库内的 `SKILL.md` 编写规范（详见各 skill 的写作说明）。

## 许可证

[MIT](./LICENSE) © 2025 Richeir
