---
type: Note
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[imani-brooks]]"
  - "[[row-level-security]]"
_organized: true
---

# Tenant Isolation FAQ For Customer Success

Short answers for customer success and Sales when a clinic asks how their data is kept separate. Written 2026-06-18 with [[imani-brooks]]; reviewed by [[abigail-ferris]] for wording.

## Answers

- **Is our data separate from other clinics?** Yes. Every record carries your account identifier, the application filters on it, and the database itself enforces the same rule on every query (row-level security), so a software bug in one place cannot show your data to another clinic.
- **Do we get our own database?** Enterprise contracts can include a dedicated database. Engineering decides eligibility ([[when-should-a-tenant-get-a-dedicated-database]]).
- **Has this been tested?** Yes, by an independent penetration test in 2026, and our controls are covered by our SOC 2 report, available under NDA.
- **Were we moved between databases this summer?** Some accounts had a short maintenance window during infrastructure work. No data was exposed or lost.

## Do Not Say

Table counts, policy names, instance names, or anything from the pen test report beyond "independent test, no cross-account access found".
