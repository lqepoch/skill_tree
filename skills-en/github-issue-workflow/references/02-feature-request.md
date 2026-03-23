---
name: Feature Request Template
about: Record a new capability, improvement suggestion, or product requirement
title: "[feature] "
labels: ["type: feature", "status: needs-triage"]
---

# Feature Request

> Use this to describe why a feature is needed, what problem it solves, what success looks like, and what is explicitly out of scope.

## 1. Summary

- One-sentence description:
- Primary beneficiaries:
- Desired outcome:

### Example

> Add bulk CSV export for the admin order list to reduce the time spent manually downloading orders.

## 2. Problem and Business Goal

Explain why this request exists.

- What pain point exists today:
- What business goal this supports:
- What happens if we do nothing:
- Why this matters to users, the team, or the process:

### Example

> Operations exports hundreds of orders every week, but currently has to page through the UI manually, which takes about 2 hours and often misses rows.

## 3. Desired Outcome

Describe what should exist after delivery.

- What users can do:
- What the system should do:
- How data, UI, or APIs should change:

### Example

> An operator can choose a date range on the order list and download a CSV containing order number, amount, status, and creation time.

## 4. Non-Goals

Make scope boundaries explicit.

- What is not included:
- What is intentionally deferred:
- What should not be solved here:

### Example

> This release only supports CSV, not customizable Excel templates, and it does not include historical data cleanup.

## 5. Constraints and Dependencies

List implementation constraints clearly.

- Technical constraints:
- Product constraints:
- Compliance or security constraints:
- External dependencies:
- Release window or timing constraints:

### Example

- Export files must stay under 10 MB
- Permission checks must remain intact
- The implementation depends on the existing async job service

## 6. Impacted Areas

List likely files, modules, or systems.

- Files:
- Modules:
- Services:
- APIs:
- Database / migration:

### Example

- `app/admin/orders/page.tsx`
- `server/export/orders.ts`
- `jobs/export-orders-worker.ts`

## 7. User Flow / Interaction

If the request affects UI or API behavior, describe the key flow.

- Entry point:
- How the user triggers the feature:
- What success looks like:
- How failures are reported:

### Example

1. Open the order list
2. Choose a date range
3. Click "Export CSV"
4. The system generates a file and provides a download link

## 8. Solution Options

Provide feasible implementation paths and the recommendation.

- Option A:
- Option B:
- Recommended option:
- Why:
- Risks:

### Example

- Option A: generate synchronously and download immediately
- Option B: generate asynchronously and notify the user when ready
- Recommended: Option B, because it is more stable for large datasets

## 9. Release / Migration Notes

If the feature affects existing users, APIs, or data, describe how to roll it out safely.

- Whether a phased rollout is needed:
- Whether old data needs migration:
- Whether backward compatibility is required:
- Whether users need to be notified:

### Example

> Keep the current API response shape unchanged and add new fields in a backward-compatible way.

## 10. Verification Plan

Describe how success will be proven before the issue is closed.

- Unit tests:
- Integration tests:
- Manual verification:
- Regression checks:

### Example

- Verify CSV row count matches filter conditions
- Confirm unauthorized users cannot export
- Confirm large exports move into queued job status

## 11. Acceptance Criteria

- [ ] The business goal is clear
- [ ] Non-goals are clear
- [ ] Constraints and dependencies are confirmed
- [ ] The solution path is selected
- [ ] Verification is defined
- [ ] The request is ready for implementation or review

## 12. Example Filled Request

### Example title

`[feature] Add CSV export for order list`

### Example body

- Summary: add CSV export for the order list
- Business goal: reduce manual export time for operations
- Desired outcome: export orders by date range in bulk
- Non-goals: no Excel support in this release
- Constraints: permission checks must remain intact; export files stay under 10 MB
- Impacted areas: frontend order list, export service, job queue
- Verification: permissions, field completeness, and large dataset behavior
- Acceptance: export output matches the selected filters
