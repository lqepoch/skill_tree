# Issue Guide

When a repository follows an issue-first workflow, the issue should be the single source of truth before implementation starts.

## When to Create an Issue First

- The user explicitly wants analysis before fixing
- The work will involve code, config, migration, regression, or release steps
- The task needs coordination, follow-up, or traceability
- Root cause, validation, or rollback details need to be recorded

## Standard Flow

1. Triage
   - Confirm the problem, impact, environment, scope, and acceptance criteria
   - If details are missing, open a triage issue and mark it `status: needs-info`
   - Do not replace facts with guesses
2. Create or update the issue
   - Prefer the issue template
   - Use a title like `[type] short summary`
   - Use the matching bug / feature / task template
3. Apply labels
   - Apply at least one `type:*`
   - Apply at least one `status:*`
   - Add `priority:*` and `area:*` when needed
4. Record progress in real time
   - Leave a progress comment at each meaningful checkpoint
   - Do not wait until the end to backfill status
   - If blocked, state the blocker immediately
5. Link the PR
   - The PR body must include references that will auto-close the issue
   - If the PR resolves multiple issues, list each one explicitly
6. Close out
   - Leave a final summary comment after verification
   - Close the issue only after the fix is verified and stable

## Required Content

Every issue should clearly state:

- What the problem, request, or task is
- Where it happens
- How to reproduce or prove it
- What the expected result is
- Why it matters
- Which files, modules, services, or configs are involved
- The recommended next step or fix
- How success will be verified
- Whether rollback or mitigation is needed

## Extra Requirements for Bugs

Bug issues should include:

- Observed behavior
- Expected behavior
- Reproduction steps
- Evidence: logs, screenshots, traces, links, or test results
- Root cause hypothesis
- Candidate fix path
- Verification plan

### Example

```text
Checkpoint: triage
Change: narrowed the issue to the payment confirmation path
Remaining: need to confirm whether retries are the trigger
Blocker: none
Evidence: request_id=...
```

## Extra Requirements for Features

Feature issues should include:

- Business goal
- Non-goals
- Constraints and dependencies
- Impacted areas
- Release or migration notes
- Acceptance criteria

## Extra Requirements for Tasks

Task issues should include:

- Deliverable
- Scope boundaries
- Likely files or systems
- Execution plan
- Verification steps
- Follow-up or rollback notes

## Progress Comment Format

Use a consistent structure so updates are easy to scan:

- `Checkpoint`
- `Change`
- `Remaining`
- `Blocker`
- `Evidence`

Recommended update points:

- triage complete
- plan confirmed
- implementation started
- validation complete
- ready to close

## PR Linkage Rules

If a PR resolves one or more issues, the PR body must include closing references such as:

- `Closes #123`
- `Fixes #123`
- `Closes owner/repo#123`

If the PR closes multiple issues, list each issue separately. Do not use one vague reference for several unrelated issues.

### Example

```text
Closes #123
Closes #124
Closes #125
```

## Template Location

Put the reference templates in `references/`, not in `assets/`.

Why:

- `references/` is the right place for readable, reusable guidance and sample content
- `assets/` is better for images, binaries, or supporting material that is not meant to be read directly
- Templates are effectively copyable instruction sets, so they fit `references/` better

## Suggested Labels

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

## Final Check

Before closing an issue, confirm:

- Facts and hypotheses are clearly separated
- Key evidence has been recorded
- The fix and verification are complete
- The PR is correctly linked to the issue
- No follow-up items were missed
