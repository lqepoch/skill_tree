---
name: github-issue-workflow
description: "面向 Codex 的 GitHub issue 优先工作流：先建 issue，再改代码；在技能入口提供简要说明、流程规则、评论规范和 PR 关联要求。"
---

# GitHub Issue 工作流

## 简介

这个 skill 用于把 GitHub issue 作为工程工作的事实源。适合在写代码前先完成 triage、记录根因假设、关联文件、制定验证和回滚方案，并在 PR 中自动关闭相关 issue。

## 何时使用

- 用户要求先分析，再修复
- 任务涉及代码、配置、迁移、回归或发布
- 需要多人协作或后续追踪
- 需要记录根因、验证和回滚信息

## 标准流程

1. Triage
   - 确认问题、影响、环境、范围和验收标准
   - 信息不足时，先开 triage issue，并标记 `status: needs-info`
   - 不要用猜测代替事实
2. 创建或更新 issue
   - 优先使用对应模板
   - 标题建议使用 `[type] 简短摘要`
3. 应用标签
   - 至少一个 `type:*`
   - 至少一个 `status:*`
   - 需要时再加 `priority:*` 和 `area:*`
4. 记录进度
   - 在 triage、方案确认、实现开始、验证完成、准备关闭等节点及时评论
   - 评论只保留当前进展，不要写成流水账
5. 关联 PR
   - PR 正文必须包含会自动关闭 issue 的引用
   - 多个 issue 要逐个列出
6. 收尾
   - 验证完成后补最终总结
   - 只在修复稳定后关闭 issue

## 评论格式

统一使用：

- `Checkpoint`
- `Change`
- `Remaining`
- `Blocker`
- `Evidence`

## PR 关联

PR 正文写：

- `Closes #123`
- `Fixes #123`
- `Closes owner/repo#123`

多个 issue 要逐个列出。

## 模板位置

参考模板放在 `references/`，而不是 `assets/`。

## 参考文件

优先阅读下面这些模板：

- `references/01-bug-report.md`
- `references/02-feature-request.md`
- `references/03-task.md`

## 标签

- `type: bug`
- `type: feature`
- `type: task`
- `type: docs`
- `status: needs-triage`
- `status: needs-info`
- `status: in-progress`
- `status: blocked`
- `priority: high`
- `priority: medium`
- `priority: low`
- `area:*`
