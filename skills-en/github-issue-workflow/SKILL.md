---
name: github-issue-workflow
description: "Issue-first GitHub workflow for Codex. Use it to create or update issues before code changes, capture root cause, related files, fix options, validation, rollback notes, maintain reusable issue templates and labels, and keep progress comments and PR closure links in sync."
---

# GitHub Issue Workflow

## Purpose

Use this skill to keep GitHub issues as the source of truth for engineering work. An issue should explain the problem, the suspected source, the files or modules involved, the recommended fix, the validation standard, and any rollback or mitigation plan.

## Operating Principles

- Treat the issue as the authoritative work item.
- Do not make code changes before the work is represented in an issue unless the user explicitly asks for exploratory analysis only.
- Write issues so another engineer can continue the work without hidden context.
- Separate facts, hypotheses, and proposed fixes.
- Prefer reusable labels and templates over project-specific ad hoc wording.
- Keep the issue open until the fix is verified and the linked PR is merged or otherwise resolved.

## Required Issue Content

Every issue should capture:

- Summary and scope
- Trigger, environment, or reproduction path
- Expected behavior
- Actual behavior or failure mode
- Impact and severity
- Suspected root cause or failure source
- Related files, modules, services, configs, or migrations
- Proposed fix options and recommendation
- Verification plan
- Rollback, mitigation, or follow-up notes
- Acceptance criteria

For bugs, always include the evidence trail. For features, include the business goal and non-goals. For tasks, include the concrete outcome and the files or systems likely to change.

## Workflow

1. Triage the request.
   - Capture the problem, scope, affected area, expected outcome, business impact, and acceptance criteria.
   - If key details are missing, open a triage issue and mark it `status: needs-info`.
   - Use the issue body or follow-up comments to record unknowns instead of guessing.
2. Open or update the issue.
   - Use GitHub issue templates.
   - Prefer a title in the form `[type] short summary`.
- Use the matching template from `references/`.
   - If the template is too small for the problem, expand the body with concrete examples, evidence, and assumptions rather than compressing the problem statement.
   - For bug issues, explicitly list:
     - suspected root cause
     - related files or modules
     - candidate fix path
     - validation method
     - rollback or mitigation
   - For feature issues, explicitly list:
     - business goal
     - constraints and dependencies
     - impacted files or services
     - rollout or migration considerations
   - For task issues, explicitly list:
     - deliverable
     - scope boundaries
     - likely files or systems
     - verification checklist
3. Apply labels.
   - Apply at least one `type:*` label and one `status:*` label.
   - Add `priority:*` when urgency is known.
   - Add `area:*` when the affected subsystem is clear.
   - Keep the label set small, stable, and reusable across repositories.
   - Do not invent a large project-specific taxonomy unless the repo already uses one.
4. Record progress.
   - Add a short comment at each meaningful checkpoint: triage complete, plan confirmed, implementation started, validation complete, ready to close.
   - Do not wait until the end; progress comments should be posted as soon as the checkpoint is reached.
   - Each update should answer:
     - what changed
     - what remains
     - whether there is a blocker
   - If the issue is blocked, state the blocker plainly and update the issue status accordingly.
5. Link the fix.
   - When a PR is ready, include `Closes #123` or `Fixes owner/repo#123` in the PR body.
   - Every PR that is expected to close work must explicitly include the relevant issue references so GitHub can auto-close them.
   - If the fix spans multiple issues, reference each one explicitly and keep the links unambiguous.
6. Finish.
   - Add a final summary comment with the shipped outcome, validation result, and any follow-up work.
   - Close the issue only after verification is complete and the resolution is durable.

## Comment Format

Use a consistent progress update format so comments are easy to scan:

- `Checkpoint`: triage, plan, implementation, validation, done
- `Change`: what was completed
- `Remaining`: what still needs work
- `Blocker`: only when something is preventing progress
- `Evidence`: logs, screenshots, links, test results, or reproduction notes

Recommended update points:

- triage complete
- plan confirmed
- implementation started
- validation complete
- ready to close

## Label Set

Use a small reusable core set first.

| Label | Color | Use |
| --- | --- | --- |
| `type: bug` | `d73a4a` | Defect or regression |
| `type: feature` | `a2eeef` | New capability |
| `type: task` | `cfd3d7` | Work item, cleanup, or follow-up |
| `type: docs` | `0075ca` | Documentation-only work |
| `status: needs-triage` | `fbca04` | Needs initial sorting |
| `status: needs-info` | `7057ff` | Missing details block progress |
| `status: in-progress` | `5319e7` | Active work |
| `status: blocked` | `d93f0b` | Blocked by dependency, decision, or external issue |
| `priority: high` | `b60205` | Urgent work |
| `priority: medium` | `fbca04` | Normal priority |
| `priority: low` | `0e8a16` | Low priority |
| `help wanted` | `008672` | Good candidate for help |
| `good first issue` | `7057ff` | Entry-level task |

- Use hex colors only.
- Keep descriptions short and consistent.
- Avoid project-specific labels unless they are clearly reusable or already established.

## Template Guidance

Prefer Markdown issue templates in `references/` for broad compatibility.

Keep a small, stable set:

- `01-bug-report.md`
- `02-feature-request.md`
- `03-task.md`

Keep the fields aligned across repositories so the same issue shape can be reused in different codebases.

For bug reports, the template should ask for:

- summary
- context and environment
- expected and actual behavior
- reproduction steps
- evidence
- suspected root cause
- related files
- fix options
- recommended fix
- verification plan
- rollback or mitigation
- acceptance criteria

For feature requests, the template should ask for:

- summary
- business goal or problem
- desired outcome
- constraints and dependencies
- affected files or systems
- rollout or migration notes
- alternatives
- acceptance criteria

For tasks, the template should ask for:

- summary
- background
- scope
- likely files or systems
- execution plan
- validation steps
- follow-up or rollback notes
- acceptance criteria

`config.yml` should only keep the issue chooser simple and uncluttered.

## Resources

- `references/issue-guide.md`
- `references/`
