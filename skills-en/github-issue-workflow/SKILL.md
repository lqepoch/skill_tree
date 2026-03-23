---
name: github-issue-workflow
description: "Issue-first GitHub workflow for Codex: create issues before code changes, capture triage, root cause, verification, labels, progress comments, and PR close links."
---

# GitHub Issue Workflow

## Summary

Use this skill to keep GitHub issues as the source of truth for engineering work. It is meant for issue-first triage, root-cause capture, file and module references, verification planning, rollback notes, progress comments, and PR linkage.

## Reference Files

Read these first:

- `references/issue-guide.md`
- `references/01-bug-report.md`
- `references/02-feature-request.md`
- `references/03-task.md`
- `references/config.yml`

## Key Rules

- Create or update an issue before implementation unless the user explicitly asks for exploratory analysis only.
- Post progress comments at meaningful checkpoints instead of backfilling at the end.
- Put `Closes #123` or `Fixes #123` in the PR body so GitHub can auto-close the issue.
- List multiple issue references explicitly and unambiguously.
- Keep the templates in `references/`, not `assets/`.
