---
name: Bug Report Template
about: Record a defect, regression, unexpected behavior, or failed verification
title: "[bug] "
labels: ["type: bug", "status: needs-triage"]
---

# Bug Report

> Use this as a working document, not just a form. The goal is to make it possible for another engineer to reproduce, diagnose, fix, and verify the issue without hidden context.
>
> If the root cause is unknown, say so explicitly and list the current hypothesis with supporting evidence.

## 1. Summary

- One-sentence description:
- One-sentence impact statement:
- Desired end state:

### Example

> Payment confirmation occasionally returns 500 on checkout, which blocks users from completing purchases.

## 2. Trigger Conditions and Environment

Describe when the issue happens as precisely as possible.

- Repository / branch:
- Environment: local / test / staging / production
- Affected service, module, page, or endpoint:
- Browser / OS / runtime / version:
- Whether it only happens for certain accounts, tenants, datasets, or regions:
- Any recent deploys, config changes, dependency upgrades, or migrations:

### Example

- Environment: production
- Page: `/checkout/confirm`
- Version: `web-2026.03.18`
- Recent change: payment gateway retry logic went live on March 21

## 3. Expected Behavior

State what should happen.

- What should the system return or render:
- What the user should see:
- Any acceptable boundary behavior:

### Example

> After clicking "Confirm Payment", the success page should appear within 2 seconds and an order number should be created.

## 4. Actual Behavior

State what is happening now.

- Error message:
- Status code / return value:
- UI behavior:
- Logs or monitoring signal:
- Gap versus expected behavior:

### Example

> The page stays in loading state, then shows "Service unavailable", and backend logs contain `PaymentService timeout`.

## 5. Reproduction Steps

Write steps that another person can execute.

1. ...
2. ...
3. ...
4. ...

### Example

1. Log in as `qa-user-01`
2. Open the cart and proceed to checkout
3. Choose credit card payment
4. Click "Confirm Payment"

## 6. Evidence

Include at least one type of evidence.

- Logs:
- Stack trace:
- Screenshot / recording:
- Dashboard:
- Request ID / trace ID:
- Related links:

### Example

```text
request_id=8f2c1e3a-7ab2-4a08-a1bf-9f8f1d0c0b11
trace_id=00-9f1d7e8b3e5b4f2fa3d3d8b6f8c0d2a1-3f5b7c1a4d2e9a0c-01
```

## 7. Impact and Severity

Explain why this matters.

- Which users, workflows, or systems are affected:
- Whether the main flow is blocked:
- Frequency:
- Data risk / money risk / compliance risk:
- Any temporary workaround:

### Example

> This blocks all credit-card users and directly impacts revenue, so severity is high.

## 8. Root Cause Hypothesis

If the root cause is still under investigation, record the current hypothesis.

- Hypothesis 1:
- Supporting evidence:
- Counter-evidence or unknowns:
- Hypothesis 2:
- Supporting evidence:
- Counter-evidence or unknowns:

### Example

- Hypothesis 1: synchronous retries are exhausting the payment connection pool
- Supporting evidence: the same request is retried 3 times in the logs
- Unknown: upstream latency has not been ruled out yet

## 9. Related Files / Modules / Services

List the areas most likely to be involved and why.

- Files:
- Modules:
- Services:
- Config:
- Migration / script:

### Example

- `src/payments/confirm.ts`: submits the payment request
- `src/lib/http/retry.ts`: controls timeout and retry behavior
- `infra/workers/payment-worker.ts`: deployment entry point

## 10. Fix Options

Provide at least one recommended path and, if useful, an alternative.

- Option A:
- Option B:
- Recommended option:
- Why:
- Risks:

### Example

- Option A: move retries out of the synchronous path
- Option B: only increase the timeout threshold
- Recommended: Option A, because it reduces both timeout and contention risk

## 11. Verification Plan

Explain how to prove the fix works.

- Unit tests:
- Integration tests:
- Manual verification:
- Monitoring checks:
- Regression checks:

### Example

- Add a unit test for payment timeout handling
- Re-run the payment flow 10 times in staging
- Confirm logs no longer show cascading retry failures

## 12. Rollback / Mitigation

If the fix is risky, explain how to reduce blast radius.

- Whether a rollback switch is needed:
- Whether config fallback is needed:
- Whether there is a temporary workaround:
- Rollback condition:

### Example

> If staging shows elevated failure rates, disable the new retry path and fall back to the previous implementation.

## 13. Acceptance Criteria

Make "done" measurable.

- [ ] Root cause is confirmed or the hypothesis is explicitly marked
- [ ] Fix option has been selected
- [ ] The change has been implemented
- [ ] Verification has passed
- [ ] Rollback / mitigation is documented
- [ ] The issue can be closed

## 14. Recommended Comment Format

Use a consistent structure in issue comments:

- `Checkpoint`: triage / plan / implementation / validation / done
- `Change`: what was completed
- `Remaining`: what still needs work
- `Blocker`: only if progress is blocked
- `Evidence`: logs, screenshots, links, test results, or reproduction notes

### Example comment

```text
Checkpoint: plan
Change: identified the payment retry path and timeout configuration as the likely failure area
Remaining: need to confirm whether this is upstream latency or local connection leakage
Blocker: none
Evidence: request_id=...
```

## 15. Example Filled Report

### Example title

`[bug] Checkout payment confirmation returns 500 after retry`

### Example body

- Summary: payment confirmation page occasionally returns 500 after retries
- Environment: production, `web-2026.03.18`
- Expected: user sees success page after payment completes
- Actual: repeated clicks end in a 500 page
- Reproduction: open cart, choose credit card, click confirm payment repeatedly
- Evidence: `request_id=...`, logs show `PaymentService timeout`
- Root cause hypothesis: synchronous retry blocks the connection pool
- Related files: `src/payments/confirm.ts`, `src/lib/http/retry.ts`
- Fix path: move retry out of the synchronous path and reduce timeout sensitivity
- Verification: unit test + repeated staging verification
- Acceptance: 10 consecutive runs succeed without 500s
