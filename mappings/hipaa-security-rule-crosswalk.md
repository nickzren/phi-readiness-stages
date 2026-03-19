# HIPAA Security Rule Crosswalk

This detailed companion crosswalk links core PRS domains to current HIPAA Security Rule standards, implementation specifications, and evidence expectations.

It is not a substitute for live source verification or legal review.

Last reviewed against official source registry: March 18, 2026.

## How to use this crosswalk

- use this file when a reviewer needs rule-level traceability
- use `mappings/hipaa-security-rule.md` for the short overview
- use `framework/stage-rubric.md` and `framework/minimum-artifact-matrix.md` for stage gating
- preserve the distinction between HIPAA baseline and stricter PRS policy choices

## Important interpretation rule

Under `45 CFR 164.306(d)`, addressable implementation specifications are not optional by default. The reviewer must evaluate whether the specification is reasonable and appropriate in the scoped environment, document the decision, and implement an equivalent alternative when reasonable and appropriate.

Use the HHS FAQ on addressable versus required implementation specifications together with the current regulation text when this distinction affects the stage decision.

## Core crosswalk

| PRS domain | First PRS stage | HIPAA citation | Rule type | Implementation status | Context note | PRS expectation | Minimum evidence type | Baseline or PRS policy |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| risk analysis and remediation | PRS-2 | `45 CFR 164.308(a)(1)(ii)(A)` and `164.308(a)(1)(ii)(B)` | implementation specification | required | scope, architecture, and deployment model drive what a thorough analysis must cover | scoped risk analysis plus tracked remediation or approved exceptions | risk analysis artifact, remediation tracker, owner assignment | HIPAA baseline |
| security responsibility | PRS-2 | `45 CFR 164.308(a)(2)` | standard | n/a | title and org structure can vary; ownership cannot be absent | named security or control owner for the workload or governing function | ownership matrix, policy assignment, operating model record | HIPAA baseline |
| workforce security | PRS-2 | `45 CFR 164.308(a)(3)` | standard plus implementation specifications | addressable for authorization or supervision, clearance, and termination procedures | reasonable-and-appropriate analysis depends on workforce model, support access, contractors, and admin paths | documented workforce access model and joiner-mover-leaver handling where relevant | workforce procedure, access review record, support-access path | HIPAA baseline |
| access control | PRS-1 | `45 CFR 164.312(a)(1)` and `164.312(a)(2)(i)-(iv)` | standard plus implementation specifications | required for unique user identification and emergency access; addressable for automatic logoff and encryption or decryption | automatic session controls and at-rest encryption decisions depend on workflow, device model, and risk analysis | role-based access, unique identities, emergency access path, and documented session or encryption decisions | IAM configuration, SSO or directory evidence, emergency access procedure, configuration screenshots | HIPAA baseline |
| audit controls | PRS-1 | `45 CFR 164.308(a)(1)(ii)(D)` and `164.312(b)` | implementation specification plus standard | required for information system activity review; audit controls standard has no separate implementation-spec label | raw logging alone is weak if there is no review path or retained record of follow-up | logging exists by PRS-1; documented review path by PRS-2; current review evidence by PRS-4 | log configuration, review procedure, sample review record, alert or investigation record | mixed: baseline for logging and review, PRS policy for stage timing |
| integrity | PRS-1 | `45 CFR 164.312(c)(1)-(2)` | standard plus implementation specification | addressable for mechanism to authenticate ePHI | exact mechanism depends on datastore, protocol, and change path | integrity protections or equivalent controls are materially implemented and explained | change-control evidence, integrity settings, database controls, signed object or hash path where used | HIPAA baseline |
| person or entity authentication | PRS-1 | `45 CFR 164.312(d)` | standard | n/a | method can vary by system and deployment model | authentication path is defined and materially enforced for relevant users and services | authentication architecture, IdP configuration, service-auth pattern | HIPAA baseline |
| transmission security | PRS-1 | `45 CFR 164.312(e)(1)-(2)` | standard plus implementation specifications | addressable for integrity controls and encryption | network type, endpoint model, and transport path affect the reasonable-and-appropriate analysis | encryption in transit is expected for PHI-bearing paths unless a clearly justified equivalent control is documented | TLS configuration, network diagram, API gateway or ingress settings, exception record | mixed: baseline for transmission security, PRS policy for default readiness bar |
| encryption and secrets handling | PRS-1 | `45 CFR 164.312(a)(2)(iv)` and `164.312(e)(2)(ii)` | implementation specification | addressable | at-rest and in-transit encryption decisions must be tied to the scoped risk analysis and environment | PRS expects encryption in transit for PHI-bearing paths and at-rest encryption or a documented compensating rationale where applicable | KMS or secrets-manager evidence, encrypted storage settings, risk decision record | mixed: HIPAA baseline plus explicit PRS policy |
| security awareness and training | PRS-2 | `45 CFR 164.308(a)(5)` | standard plus implementation specifications | addressable for reminders, malicious-software protection, log-in monitoring, and password management | content and cadence vary by size, role, and system profile | workforce readiness path exists before PHI approval; completed or assigned training is evidenced where relevant | training policy, assigned training record, phishing or awareness cadence, secure-password path | HIPAA baseline |
| security incident response | PRS-2 | `45 CFR 164.308(a)(6)(ii)` | implementation specification | required | incident process must fit system criticality and operating model | incident response and reporting path are documented before approval and evidenced in live operations | incident procedure, escalation path, incident ticket examples, on-call ownership | HIPAA baseline |
| contingency and restore confidence | PRS-2 | `45 CFR 164.308(a)(7)(ii)(A)-(E)` | implementation specifications | required for backup, disaster recovery, and emergency mode; addressable for testing and revision procedures and applications and data criticality analysis | backup strategy, restore testing, and emergency operations should fit system recovery needs and deployment model | backup and restore approach is documented by PRS-1; restore evidence and contingency procedure by PRS-2; current confidence evidence by PRS-4 | backup policy, restore test record, disaster recovery procedure, criticality analysis | mixed: baseline for core plans, PRS policy for explicit restore-confidence emphasis |
| periodic evaluation | PRS-4 | `45 CFR 164.308(a)(8)` and `164.306(e)` | standard plus general maintenance rule | n/a | cadence should reflect operational and environmental change, not a fixed universal schedule | evaluation becomes stage-critical once PHI is live; pre-live reassessment still matters when architecture changes materially | evaluation record, reassessment memo, post-change review evidence | HIPAA baseline |
| physical safeguards | PRS-1 | `45 CFR 164.310(a)-(d)` | standards plus implementation specifications | required for disposal and media re-use; addressable for facility access-control details, accountability, and backup before movement | cloud-only workloads may inherit much of this, but retained responsibilities still need to be named | direct or inherited physical responsibilities are identified early; unresolved retained duties cap the stage | shared-responsibility record, facility control evidence, workstation guidance, device or media procedure | HIPAA baseline |
| vendor management and BAA analysis | PRS-3 | `45 CFR 164.308(b)(3)` and `164.314(a)` | implementation specification | required | contract path depends on role, customer model, and whether the vendor creates, receives, maintains, or transmits ePHI | required BA or subcontractor assurance path must be complete before PRS-3 | signed BAA or equivalent arrangement, vendor inventory, subprocessor review record | HIPAA baseline |
| policies, procedures, and documentation retention | PRS-2 | `45 CFR 164.316(a)-(b)` | standard plus implementation specifications | required for time limit, availability, and updates | the six-year retention rule applies to required security documentation, but storage model and indexing can vary | minimum stage artifacts must be durable, reviewable, and kept current; PRS also expects evidence pointers for repeatable reviews | policy index, evidence-retention map, record-location index, update history | mixed: baseline for retention and updates, PRS policy for evidence-location discipline |

## Rows that often need explicit PRS policy labeling

- encryption expectations at PRS-1
- the amount of live operational evidence needed before PRS-4
- the amount of restore-test confidence needed before PRS-2 or PRS-4

When PRS uses a stricter bar than the rule itself, say so explicitly in the assessment.
