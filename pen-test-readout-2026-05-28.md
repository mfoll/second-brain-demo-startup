---
type: Event
date: 2026-05-28
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[ivo-radic]]"
  - "[[bracken-hollow-pen-test-report-2026]]"
  - "[[security-and-privacy]]"
_organized: true
---

# Pen Test Readout 2026-05-28

Readout of the 2026 penetration test by [[ivo-radic]] of Bracken Hollow Security. Me, Teodora, Kwabena, Min-jae and [[colette-fairbanks]] for the SOC 2 record.

## Result

- Main objective: could an admin user of one tenant reach another tenant's data? Not achieved through the web app or API, in the shared schema or in the tenant databases.
- One medium finding: some API error responses included internal error details. Fixed in QL-1561 on 2026-06-03; retest clean on 2026-06-10.
- Three informational notes on security headers, all fixed by 2026-06-20.

Details stay in [[bracken-hollow-pen-test-report-2026]], which points to the report in the SOC 2 evidence folder.

## Why It Mattered

Ivo said plainly that a test cannot prove isolation, only fail to break it. Still, the shared schema had held up against a tester trying hard, which weakened the main argument for moving every small tenant at our cost. It went into the pre-read for [[architecture-review-2026-06-11]].

## Follow-up

- Evidence for the [[soc2-type-1-audit]] filed by Colette.
- Next test planned before the Type II report in 2027.
