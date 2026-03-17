# Output Contract

Every PRS assessment must return the following sections in order.

## 1. Scoped summary

- workload or system name
- environment
- deployment boundary
- assessed date
- reviewer

## 2. Applicability and role

- whether PHI or ePHI is in scope now, planned later, or explicitly out of scope
- likely role: covered entity, business associate, subcontractor, outside HIPAA scope, or unclear
- rationale and caveats

## 3. Evidence reviewed

- evidence grouped by level from `framework/evidence-levels.md`
- evidence freshness from `framework/evidence-freshness.md`
- evidence gaps
- explicit note if review is repo-only

## 4. Official sources verified

For each source used:

- title
- URL
- source type: law, official guidance, implementation guidance
- access date

## 5. Current stage assignment

- exact PRS stage code and frozen public label
- confidence: high, medium, or low
- concise explanation of why the stage is not lower
- concise explanation of why the stage is not higher

## 6. Domain findings

For each required domain relevant to the next candidate stage:

- status: met, partial, missing, or unclear
- observed evidence
- blockers

## 7. Recommended actions

Ordered by priority:

- action
- why it matters
- evidence artifact expected after completion
- stage impact

## 8. Caveats

- no legal determination
- no certification claim
- any scope or evidence limitations

## 9. Regulatory boundary note

- whether adjacent Privacy Rule, Breach Notification Rule, state law, FTC, or other review is still needed
- whether the assessment is limited to Security Rule-oriented readiness

## 10. Safe public wording

Provide one short public-safe statement using the exact frozen public label.
