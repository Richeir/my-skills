---
name: commit-conventions
description: 当在一个会产生 git 提交的项目中工作时使用，以确保你创建的每条提交信息都保持一致、格式正确。
---

# 提交规范

## 概述

每次 git 提交都必须遵循 **Angular / Conventional Commits** 格式。不符合模板的提交信息就是不合格的提交信息。

## 何时使用

- 编写或改写任何提交信息
- 推送前审查提交信息
- 代表用户创建提交
- 适用于所有项目，无例外

## 快速参考

```
<type>(<scope>): <subject>

<body>
```

| 部分 | 规则 |
|------|------|
| `type` | 小写；只能是下表之一（必填） |
| `scope` | 可选；小写，用 `()` 包住 |
| `subject` | 英文、祈使句、小写开头、结尾不加句号、≤ 50 字符 |
| `body` | 与 subject 之间空行分隔；每行 ≤ 72 字符；破坏性变更标注 `BREAKING CHANGE:` |

### Type 类型

| type | 用途 |
|------|------|
| `feat` | 新增功能/文件 |
| `fix` | 修复缺陷 |
| `docs` | 仅文档变更 |
| `refactor` | 重构（不改行为） |
| `chore` | 杂项（依赖、配置、构建） |
| `style` | 格式/排版，不影响逻辑 |
| `test` | 测试相关 |
| `perf` | 性能优化 |
| `build` | 构建系统或外部依赖变更 |
| `ci` | CI 配置变更 |

## 示例

```text
feat(demo): add forecast query

demo.py now logs in and queries representative APIs per category,
printing real return values (error_code/fields/data).
```

## 常见错误

- type 大写（`Feat:`）—— type 必须小写
- subject 大写开头（"Add ..."）—— subject 应小写开头
- subject 结尾加句号 —— subject 结尾不加 `.`
- 把整个 diff 粘贴作为提交信息 —— 应概括意图而非变更本身
- 需要背景时省略 body —— 用空行分隔，每行 ≤ 72 字符
