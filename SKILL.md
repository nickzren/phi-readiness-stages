---
name: phi-readiness-stages
description: Assess the current PHI Readiness Stage (PRS) of a workload, repository, system, or environment; determine HIPAA applicability and role; identify evidence gaps; and recommend next actions using official HHS/OCR and NIST sources with conservative evidence caps.
version: 1.0.0
metadata:
  openclaw:
    homepage: https://github.com/nickzren/phi-readiness-stages
    skillKey: phi-readiness-stages
---

# PHI Readiness Stages

This top-level `SKILL.md` is the canonical install and publish entrypoint for the repository root.

It is suitable for Codex, Claude Code, and OpenClaw-compatible registries that publish a root skill folder directly.

The detailed PRS assessment workflow lives in `skills/phi-readiness-review/SKILL.md`.

If you are using this as an installed or published skill, always load files in this order:

1. `skills/phi-readiness-review/SKILL.md`
2. `framework/assessment-rules.md`
3. `framework/applicability-role-matrix.md`
4. `framework/stage-rubric.md`
5. `framework/evidence-levels.md`
6. `framework/evidence-freshness.md`
7. `framework/minimum-artifact-matrix.md`
8. `framework/regulatory-boundaries.md`
9. `framework/output-contract.md`

Then load only the additional control, checklist, and reference files needed for the specific assessment.

If you are using the repository itself as context rather than as an installed skill, start from `AGENTS.md`.
