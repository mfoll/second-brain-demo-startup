---
type: Person
related_to:
  - "[[bracken-hollow-pen-test-report-2026]]"
  - "[[pen-test-readout-2026-05-28]]"
  - "[[secure-and-comply]]"
_organized: true
---

# Ivo Radic

Penetration tester; runs Bracken Hollow Security, an independent practice. Tested Quaylane in 2026-05.

## Engagement

- Scope: the web app and API, authenticated as admin users of two test tenants, with a specific objective to reach data of another tenant. Testing ran 2026-05-04 to 2026-05-15.
- Readout on 2026-05-28 ([[pen-test-readout-2026-05-28]]); report in [[bracken-hollow-pen-test-report-2026]].
- Result: no cross-tenant access found in the shared schema. One finding on verbose error messages (stack details in some API 500 responses), fixed in QL-1561 on 2026-06-03 and retested clean.

## Why It Mattered

The finding that the shared schema held up was one of the inputs to [[architecture-review-2026-06-11]]. It did not prove isolation; it showed that the risk we were paying $3,100 a month to remove was smaller than we had assumed.

## How We Work Together

Clear scoping call before the test, short written updates during it, and he explains findings to engineers without drama. We plan to use him again before the SOC 2 Type II report in 2027.
