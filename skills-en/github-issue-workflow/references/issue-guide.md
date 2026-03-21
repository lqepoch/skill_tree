# Issue Guide

Use this skill when the repository should follow an issue-first workflow.

## Issue Anatomy

Every well-formed issue should explain:

- What is broken, missing, or being requested
- Where it happens
- How to reproduce or prove it
- What the expected outcome is
- Why it matters
- What files, modules, services, configs, or migrations are likely involved
- What the recommended fix or next step is
- How success will be validated
- Whether rollback or mitigation is needed

If the root cause is not confirmed, label it as a hypothesis and include the evidence that supports it.

## Bug Standard

Bug issues should document:

- observed behavior
- expected behavior
- environment details
- reproduction steps
- logs, traces, screenshots, or links
- suspected source of failure
- related files and why they are implicated
- candidate fixes and why one is preferred
- verification and rollback plan

If multiple failure sources are possible, list them in priority order and explain how each was ruled in or out.

## Feature Standard

Feature issues should document:

- business goal or user need
- why the current behavior is insufficient
- scope and non-goals
- constraints and dependencies
- impacted files or systems
- rollout, migration, or compatibility concerns
- alternatives considered
- acceptance criteria

## Task Standard

Task issues should document:

- the concrete deliverable
- the reason the task exists
- scope boundaries
- likely files or systems to touch
- implementation plan
- validation steps
- follow-up or cleanup items

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

If the root cause is still under investigation, mention the current leading hypotheses and the next check you plan to run.

## PR Linkage

When the change is ready, put `Closes #<issue>` or `Fixes owner/repo#<issue>` in the pull request body.
Use that linkage instead of manual closure when possible.
If a change closes multiple issues, list every issue explicitly.
