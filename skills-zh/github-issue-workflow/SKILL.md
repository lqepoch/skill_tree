---
name: github-issue-workflow
description: "GitHub issue 优先工作流，适用于在 Codex 中先创建或更新 GitHub issue，再用 GitHub MCP 维护模板、标签体系和进度评论的场景。用于需要先在 GitHub 追踪工作、创建或整理 issue 模板与标签、或将实现进度同步回 issue 的任务。"
---

# GitHub 问题工作流

## 核心规则

- 将 issue 视为唯一事实源。
- 如果工作尚未被追踪，先创建或更新 issue，再修改代码。
- 在修复验证完成前，持续保持 issue 更新。

## 工作流

1. 先做分诊。
   - 记录问题、范围、仓库区域、预期结果、影响范围和验收标准。
   - 如果信息不足，先创建一个分诊 issue，并标记为 `status: needs-info`。
2. 创建或更新 issue。
   - 使用 GitHub MCP 的 `issue_write` 创建或更新 issue。
   - 标题建议采用 `[type] 简短摘要`。
   - 使用 `assets/github-issue-templates/` 中对应的模板。
3. 应用标签。
   - 至少添加一个 `type:*` 标签和一个 `status:*` 标签。
   - 在已知的情况下，再添加 `priority:*` 和 `area:*` 标签。
   - 标签保持通用，便于在不同仓库复用。
4. 同步进度。
   - 在每个关键节点补一条简短评论：分诊、计划、实现、验证、完成。
   - 每条评论都写清楚：改了什么、还剩什么、是否被阻塞。
5. 关联修复。
   - 准备合并时，在 PR 描述中写入 `Closes #123` 或 `Fixes owner/repo#123`。
   - 尽量用这种关联方式在合并后自动关闭 issue。
6. 收尾。
   - 添加最终总结评论。
   - 只有在验证完成后，才关闭 issue。

## 标签集

先用一组小而稳定的核心标签。

| 标签 | 颜色 | 用途 |
| --- | --- | --- |
| `type: bug` | `d73a4a` | 缺陷或回归 |
| `type: feature` | `a2eeef` | 新能力 |
| `type: task` | `cfd3d7` | 任务或清理工作 |
| `type: docs` | `0075ca` | 仅文档工作 |
| `status: needs-triage` | `fbca04` | 需要初步分诊 |
| `status: needs-info` | `7057ff` | 等待补充信息 |
| `status: in-progress` | `5319e7` | 正在处理 |
| `status: blocked` | `d93f0b` | 被外部条件阻塞 |
| `priority: high` | `b60205` | 高优先级 |
| `priority: medium` | `fbca04` | 中优先级 |
| `priority: low` | `0e8a16` | 低优先级 |
| `help wanted` | `008672` | 适合协作 |
| `good first issue` | `7057ff` | 适合作为入门任务 |

- 只使用 6 位十六进制颜色。
- 标签描述保持简短、稳定。
- 不要引入过多项目私有标签，除非它们能跨仓库复用。

## 模板

- 优先使用 `.github/ISSUE_TEMPLATE/` 下的 Markdown issue 模板。
- 为了兼容性，尽量不要只依赖复杂表单。
- 模板字段保持稳定：摘要、上下文、预期、实际、验收标准、链接、环境。
- 文件名使用明确顺序，例如 `01-bug-report.md`、`02-feature-request.md`、`03-task.md`。
- `config.yml` 只保留简单的模板选择行为。

## 资源

- `references/issue-guide.md`
- `assets/github-issue-templates/`