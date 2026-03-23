# Issue Guide

When a repository uses an issue-first workflow, write the issue before implementation starts.

## When to Use It

- The user wants analysis before a fix
- The work involves code, config, migration, regression, or release steps
- The task needs coordination or follow-up
- Root cause, validation, or rollback details must be recorded

## Flow

1. Triage
   - Confirm the problem, impact, environment, scope, and acceptance criteria
   - If details are missing, open a triage issue and mark it `status: needs-info`
2. Create or update the issue
   - Prefer the matching template
   - Use a title like `[type] short summary`
3. Apply labels
   - Add at least one `type:*`
   - Add at least one `status:*`
   - Add `priority:*` and `area:*` when needed
4. Record progress
   - Add comments at meaningful checkpoints
   - Do not wait until the end to backfill status
5. Link the PR
   - Include auto-closing references in the PR body
   - List multiple issues explicitly
6. Close out
   - Add a final summary comment
   - Close the issue only after the fix is verified and stable

## Comment Format

Use:

- `Checkpoint`
- `Change`
- `Remaining`
- `Blocker`
- `Evidence`

## PR Linkage

Use one or more of:

- `Closes #123`
- `Fixes #123`
- `Closes owner/repo#123`

## Template Location

Put reference templates in `references/`, not `assets/`.

## Labels

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
