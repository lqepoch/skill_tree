---
name: github-issue-workflow
description: "面向 Codex 的 GitHub issue 优先工作流：先建 issue，再改代码；沉淀 bug / feature / task 的流程、标签、进度评论和 PR 关闭关联。"
---

# GitHub Issue 工作流

## 简介

这个 skill 用于把 GitHub issue 作为工程工作的事实源。适合在写代码前先完成 triage、记录根因假设、关联文件、制定验证和回滚方案，并在 PR 中自动关闭相关 issue。

## 参考文件

优先阅读下面这些参考文件：

- `references/issue-guide.md`
- `references/01-bug-report.md`
- `references/02-feature-request.md`
- `references/03-task.md`
- `references/config.yml`

## 使用要点

- 先建 issue，再开始实现，除非用户明确只要求探索性分析。
- issue 评论要在关键 checkpoint 及时更新，不要等到最后回填。
- PR 正文必须写入 `Closes #123`、`Fixes #123` 之类的自动关闭引用。
- 多个 issue 要逐个写清楚，避免歧义。
- 模板正文放在 `references/`，不要放到 `assets/`。
