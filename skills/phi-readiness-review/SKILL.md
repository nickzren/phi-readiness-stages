---
name: phi-readiness-review
description: Assess the current PHI Readiness Stage (PRS) of a workload, repository, system, or environment; determine HIPAA applicability and role; identify evidence gaps; and recommend the next actions using the PRS framework, official HHS/OCR and NIST sources, and conservative evidence caps.
---

# PHI Readiness Review

Use this skill when the task is to assess a system's PRS stage, check PHI-readiness gaps, audit evidence for PHI use, or recommend the next steps to advance a workload safely.

## Load order

Always read these first:

1. `framework/assessment-rules.md`
2. `framework/applicability-role-matrix.md`
3. `framework/stage-rubric.md`
4. `framework/evidence-levels.md`
5. `framework/evidence-freshness.md`
6. `framework/minimum-artifact-matrix.md`
7. `framework/regulatory-boundaries.md`
8. `framework/output-contract.md`

Then read only the references needed for the task:

- `skills/phi-readiness-review/references/triage.md` for HIPAA applicability and role
- `skills/phi-readiness-review/references/checklist.md` for the full review sequence
- `skills/phi-readiness-review/references/report-template.md` for the output layout
- `skills/phi-readiness-review/references/action-priority.md` for ordering recommendations
- `controls/index.md` and specific control files for domain-level questions
- `controls/shared-responsibility.md` for cloud, SaaS, customer-hosted, or inherited-control reviews
- `controls/physical-safeguards.md` when facilities, devices, workstations, media handling, or retained physical responsibilities are in scope
- `references/source-registry.md` before making claims about current HIPAA rules

## Required workflow

1. Define the exact workload, environment, and deployment boundary under review.
2. Determine whether PHI or ePHI is in scope now, later, or explicitly excluded.
3. Determine the likely HIPAA role or say that it is unclear.
4. Inventory evidence and classify it using `framework/evidence-levels.md`.
5. Check evidence freshness using `framework/evidence-freshness.md`.
6. Verify that the minimum artifact set for the candidate stage exists using `framework/minimum-artifact-matrix.md`.
7. Verify current official sources live from `references/source-registry.md`.
8. Evaluate each required domain for the candidate stage using `framework/stage-rubric.md`.
9. Use `controls/shared-responsibility.md` whenever controls are inherited or the deployment model changes the role analysis.
10. Use `controls/physical-safeguards.md` whenever physical controls are direct, partially inherited, or unclear.
11. Add a regulatory-boundary note using `framework/regulatory-boundaries.md`.
12. Apply conservative stage caps when evidence is missing, stale, indirect, or role-dependent.
13. Assign the highest defensible stage.
14. Recommend the next actions required to reach the next stage.
15. Return the assessment using `framework/output-contract.md`.

## Hard constraints

- Do not overrule the evidence cap with technical optimism.
- Do not infer approval, contracting, or live operations from code.
- Do not infer covered-entity, business-associate, or subcontractor status from branding alone.
- Do not use proposed NPRM changes as current mandatory requirements unless asked for a forward-looking analysis.
- Do not use `HIPAA compliant`, `HIPAA certified`, or `HIPAA secure` as status labels.
- If the review is repo-only, say so explicitly.
- If adjacent Privacy Rule, Breach Notification Rule, FTC, or state-law issues are implicated, flag them explicitly instead of silently folding them into the PRS stage.

## Escalation logic

- If the workload is clearly out of PHI scope, stop at PRS-0 unless the task explicitly asks for future-state readiness.
- If technical safeguards exist but governance evidence is missing, cap at PRS-1.
- If governance evidence exists but explicit approval is missing, cap at PRS-2.
- If approval exists but live PHI evidence is missing, cap at PRS-3.
- If live evidence is stale or controls appear lapsed, call for reassessment and possible downgrade.
