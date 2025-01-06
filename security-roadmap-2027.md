---
type: Note
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[soc2-type-2-observation]]"
  - "[[owasp-application-security-verification-standard]]"
  - "[[engineering-budget-2027]]"
_organized: true
---

# Security Roadmap 2027

Draft of what the security program should achieve in 2027, to sit beside the product roadmap. Started 2026-10-12.

## Must

- SOC 2 Type II report for 2026-09-01 to 2027-02-28, issued about 2027-04, then a 12-month window from 2027-03-01.
- Annual penetration test before 2027-02-28, scoped to include dedicated enterprise databases and the SSO flows.
- Row-level security on all 47 tenant-scoped tables (41 today), tracked by [[row-level-security-rollout]].
- Reminder log retention decided and enforced ([[how-long-should-we-retain-reminder-message-logs]]).

## Should

- Measure the web app against ASVS level 1 requirements as a self-assessment, starting with authentication and access control ([[owasp-application-security-verification-standard]]).
- A shorter error message policy: the one pen test finding on verbose error messages is fixed, but we have no rule preventing its return ([[owasp-top-10-2025]] A10).
- Security awareness training twice a year instead of once, with a phishing exercise ([[althobaiti-2024-review-of-organization-oriented-phishing-research]]).

## Could

- A public security page with the subprocessor list and how to request the SOC 2 report.
- ISO 27001, only if the revisit conditions in [[do-we-need-iso-27001-as-well-as-soc-2]] are met.

## Not in 2027

Bug bounty program. Too much triage load for a team of ten.
