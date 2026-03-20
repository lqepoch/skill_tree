# Issue Guide

Use this skill when the repository should follow an issue-first workflow.

## Template Rules

- Prefer Markdown issue templates for broad compatibility.
- Keep fields stable across repositories.
- Use a small template set:
  - `01-bug-report.md`
  - `02-feature-request.md`
  - `03-task.md`
- Include a simple `config.yml` so the issue chooser stays clean.

## Label Rules

- Keep the core taxonomy small.
- Use the same label names across repositories when possible.
- Prefer these families:
  - `type:*`
  - `status:*`
  - `priority:*`
  - `area:*`
- Keep label colors readable and distinct.
- Use 6-digit hex colors only.

## Comment Cadence

Post a progress comment when the work moves between clear stages:

- triage complete
- plan confirmed
- implementation started
- validation complete
- ready to close

Each comment should answer:

- what changed
- what remains
- whether anything is blocked

## PR Linkage

When the change is ready, put `Closes #<issue>` or `Fixes owner/repo#<issue>` in the pull request body.
Use that linkage instead of manual closure when possible.
