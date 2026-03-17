# Applicability and Role Triage

Use this reference when the scope or HIPAA role is ambiguous.

Read this with `framework/applicability-role-matrix.md`.

## Questions to answer

- Does the workload receive, maintain, transmit, process, or store PHI or ePHI now?
- Is the workload being prepared to do so later?
- Is the organization operating as a covered entity, business associate, subcontractor, or as infrastructure outside HIPAA scope for the specific workflow?
- Is the answer dependent on a contract, customer deployment model, or service boundary that has not been shown?
- Are inherited controls or support access changing the role analysis?

## Conservative defaults

- If PHI handling is only hypothetical and the current workload is restricted to non-PHI, treat the current state as PRS-0 or PRS-1 depending on implementation intent.
- If role depends on contract structure not provided, say `likely` and reduce confidence.
- If a vendor provides only commodity tooling with no access to PHI in the scoped model, do not assume BA status without evidence.
- If a service stores or can access customer ePHI as part of its function, treat BA analysis as likely relevant and require evidence.
- If deployment model changes the answer, split the assessment by deployment boundary.

## Role output language

Use one of:

- likely covered entity
- likely business associate
- likely subcontractor
- likely outside HIPAA scope for the reviewed workflow
- unclear from available evidence
