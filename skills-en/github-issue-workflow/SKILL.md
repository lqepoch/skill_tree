---
name: github-issue-workflow
description: "GitHub issue-first workflow for Codex: create or update issues before coding, manage issue templates and reusable label taxonomies, and add progress comments through GitHub MCP. Use when work should be tracked in GitHub, when creating or refining issue templates or labels, or when reporting implementation progress back to an issue."
---

# GitHub Issue Workflow

## Core Rule

- Treat the issue as the source of truth.
- If the work is not already tracked, create or update the issue before making code changes.
- Keep the issue updated until the fix is verified.

## Workflow

1. Triage the request.
   - Capture problem, scope, repo area, expected outcome, impact, and acceptance criteria.
   - If details are missing, create a triage issue and mark it `status: needs-info`.
2. Open or update the issue.
   - Use GitHub MCP `issue_write` to create or update the issue.
   - Prefer a title like `[type] short summary`.
   - Use the matching template from `assets/github-issue-templates/`.
3. Apply labels.
   - Apply at least one `type:*` label and one `status:*` label.
   - Add `priority:*` and `area:*` labels when they are known.
   - Keep labels generic so they work across repositories.
4. Report progress.
   - Add a short comment at each meaningful checkpoint: triage, plan, implementation, validation, done.
   - Keep each update factual: what changed, what remains, and any blocker.
5. Link the fix.
   - Put `Closes #123` or `Fixes owner/repo#123` in the pull request body when the change is ready.
   - Use the linked PR to close the issue automatically after merge.
6. Finish.
   - Add a final summary comment.
   - Close the issue only after verification is complete.

## Label Set

Use a small, reusable core set first.

| Label | Color | Use |
| --- | --- | --- |
| `type: bug` | `d73a4a` | Defect or regression |
| `type: feature` | `a2eeef` | New capability |
| `type: task` | `cfd3d7` | Work item or cleanup |
| `type: docs` | `0075ca` | Documentation-only work |
| `status: needs-triage` | `fbca04` | Needs initial sorting |
| `status: needs-info` | `7057ff` | Waiting on missing details |
| `status: in-progress` | `5319e7` | Active work |
| `status: blocked` | `d93f0b` | Stopped by an external blocker |
| `priority: high` | `b60205` | Urgent work |
| `priority: medium` | `fbca04` | Normal priority |
| `priority: low` | `0e8a16` | Low priority |
| `help wanted` | `008672` | Good candidate for help |
| `good first issue` | `7057ff` | Easy entry point |

- Use hex colors only.
- Keep descriptions short and consistent.
- Do not overload the repository with project-specific labels unless they are clearly reusable.

## Templates

- Prefer issue templates in `.github/ISSUE_TEMPLATE/`.
- Use Markdown templates for maximum compatibility across repositories.
- Keep template sections stable: summary, context, expected, actual, acceptance criteria, links, environment.
- Keep filename order explicit, for example `01-bug-report.md`, `02-feature-request.md`, `03-task.md`.
- Use `config.yml` only for simple chooser behavior.

## Resources

- `references/issue-guide.md`
- `assets/github-issue-templates/`
