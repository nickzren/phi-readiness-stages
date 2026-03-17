# Assessment Rules

This document defines the required behavior for any agent or reviewer using PRS.

## 1. Start with applicability

Before assigning a stage, determine:

- whether the scoped workload is intended to receive, maintain, transmit, process, or store PHI or ePHI
- whether the organization appears to act as a covered entity, business associate, subcontractor, or outside HIPAA scope for the reviewed workflow
- whether the review target is a repository, a deployed environment, a specific workload, or only a subset of those

If applicability or role is unclear, say so explicitly and lower confidence.

Use `framework/applicability-role-matrix.md`.

## 2. Use live source verification

For any statement about current HIPAA rules, current HHS/OCR guidance, or current NIST guidance:

- verify the source live from `references/source-registry.md`
- cite the source URL
- include the access date
- distinguish binding law, official guidance, and implementation guidance

Never treat proposed rules as current requirements unless the user explicitly requests proposed-state analysis.

## 3. Separate evidence from inference

Mark every important point as one of:

- observed
- documented
- inferred
- missing

Inferred points may guide questions and next steps. They cannot close mandatory criteria by themselves.

## 4. Apply conservative caps

- Repo-only evidence can support PRS-0 or PRS-1.
- PRS-2 requires non-code process and governance evidence.
- PRS-3 requires explicit approval and required contractual evidence.
- PRS-4 requires live operational evidence and current maintenance evidence.

If evidence type is insufficient for the candidate stage, assign the highest lower stage supported by the available evidence.

## 5. Check evidence freshness

Use `framework/evidence-freshness.md`.

- Current evidence can support the current stage.
- Aging evidence lowers confidence.
- Stale or invalidated evidence cannot, by itself, support the current stage.

## 6. Require minimum artifacts

Use `framework/minimum-artifact-matrix.md`.

If the minimum artifact set for a candidate stage is not materially present, do not assign that stage.

## 7. Evaluate by required domains

The minimum domains are defined in `framework/stage-rubric.md`. Do not average scores or let strong technical controls outweigh missing approval, process, or live-operations evidence.

## 8. Evaluate inherited controls explicitly

If the workload inherits controls from cloud, SaaS, a central platform, or a customer-hosted model:

- use `controls/shared-responsibility.md`
- identify what is inherited and what remains the workload owner's responsibility
- do not let provider branding or certification substitute for workload evidence

## 9. Respect regulatory boundaries

Use `framework/regulatory-boundaries.md`.

PRS primarily answers a Security Rule-oriented readiness question. It does not, by itself, resolve full Privacy Rule, Breach Notification Rule, FTC, or state-law compliance.

## 10. Use exact stage language

Use the exact stage code and frozen public label on first mention. After that, the code alone is acceptable.

Avoid:

- HIPAA compliant
- HIPAA-ready
- HIPAA certified
- HIPAA secure

Use:

- PRS-1 Security-Aligned - not approved for PHI
- PRS-2 PHI-Ready - pending internal approval

## 11. Require explicit scope in the final answer

Every final stage statement must specify:

- workload name
- environment
- whether PHI is in scope now, later, or not at all
- evidence basis
- next review trigger

## 12. Produce action-oriented findings

Recommendations must:

- map directly to missing or weak required domains
- be ordered by stage-gating impact and risk reduction
- name the evidence artifact that should exist after the action is complete

## 13. Handle downgrade conditions

If evidence shows control lapse, stale evidence, material architecture change, or unclear ownership, call for reassessment and possible downgrade.
