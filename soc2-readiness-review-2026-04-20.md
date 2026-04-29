---
type: Event
date: 2026-04-20
belongs_to: "[[soc2-type-1-audit]]"
related_to:
  - "[[soc2-control-matrix]]"
  - "[[patrice-ndour]]"
  - "[[soc2-readiness-assessment-2026-04]]"
_organized: true
---

# SOC 2 Readiness Review 2026-04-20

A two-day readiness review by Ashcombe Assurance, 2026-04-20 and 2026-04-21, against the draft [[soc2-control-matrix]]. Patrice's team walked through each control with its owner and asked for one example of evidence.

## Result

11 of 58 controls marked as gaps ([[soc2-readiness-assessment-2026-04]]):

- Change management: the new review rule had been adopted on 2026-04-08 but branch protection was not yet enforced on `quaylane-infra`. Fixed 2026-04-30.
- No written information security policy approved by management. [[information-security-policy]] approved 2026-05-12.
- No vendor risk process. [[vendor-risk-register]] created by Colette, first reviews 2026-05.
- No penetration test in the last 12 months. Commissioned from Bracken Hollow Security; report 2026-05 ([[bracken-hollow-pen-test-report-2026]]).
- No security awareness training records. First training run 2026-06 ([[security-awareness-training-records]]).
- No incident response plan for security incidents (the outage runbook covered availability only). [[security-incident-response-plan]] written 2026-06.
- Backup restore never tested end to end. First restore test 2026-06-09.
- Access review designed but never run.
- Offboarding checklist missing device steps.
- Two smaller rows on logging retention and the asset inventory.

## What Happened Next

9 of the 11 were closed before the as-of date of 2026-07-31. The two left open, the access review and the device step of offboarding, are exactly the two exceptions in the [[soc2-type-1-report]]. I knew in April which two were at risk and still let them slip behind the visible work. See [[lessons-from-the-soc2-type-1-audit]].
