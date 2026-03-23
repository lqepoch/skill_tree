---
name: Task Template
about: Record cleanup, follow-up work, migration, documentation, splitting work, or any clearly bounded deliverable
title: "[task] "
labels: ["type: task", "status: needs-triage"]
---

# Task

> Use this for concrete deliverables with a clear scope, validation plan, and follow-up path. Avoid vague wording such as "clean things up" without boundaries.

## 1. Summary

- One-sentence description:
- Deliverable:
- Desired end state:

### Example

> Remove unused experimental code from the order service and add the corresponding maintenance note.

## 2. Background

Explain why the task exists.

- Trigger:
- Current pain point:
- Relevant context or decision history:

### Example

> The old experiment code adds noise during debugging and is no longer used by any traffic.

## 3. Scope

State what is included and excluded.

- In scope:
- Out of scope:
- Boundary conditions:

### Example

- In scope: remove unused feature flag branches
- Out of scope: refactor the core order flow

## 4. Likely Files / Systems

List the places you expect to touch.

- Files:
- Modules:
- Services:
- Config:

### Example

- `src/orders/legacy.ts`
- `docs/orders-maintenance.md`

## 5. Execution Plan

Break the task into steps.

1. ...
2. ...
3. ...

### Example

1. Confirm there are no runtime dependencies
2. Delete stale branches and invalid config
3. Update documentation

## 6. Verification

Describe how completion will be verified.

- Automated checks:
- Manual checks:
- Regression checks:

### Example

- Run relevant tests
- Confirm the build passes
- Search the repo for remaining references

## 7. Follow-up / Rollback

If the task carries risk, explain the fallback path.

- Rollback path:
- Follow-up notes:
- Whether additional tasks are expected:

### Example

> If removal reveals an untracked call site, restore the file first and then add the missing reference cleanup.

## 8. Acceptance Criteria

- [ ] The scope is clear
- [ ] The deliverable is complete
- [ ] Verification has passed
- [ ] Follow-up items are documented

## 9. Example Filled Task

### Example title

`[task] Remove unused order feature flag code`

### Example body

- Summary: remove unused order experiment code
- Background: the code is no longer used and adds maintenance cost
- Scope: delete only unused branches and related config, without changing the core flow
- Likely files: `src/orders/legacy.ts`, `docs/orders-maintenance.md`
- Execution plan: confirm no references -> delete -> update docs -> verify build
- Verification: tests pass and no references remain
- Follow-up: restore and re-clean if any missed references appear
