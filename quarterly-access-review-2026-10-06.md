---
type: Event
date: 2026-10-06
belongs_to: "[[soc2-type-2-observation]]"
related_to:
  - "[[run-the-quarterly-access-review]]"
  - "[[access-review-log]]"
  - "[[principle-of-least-privilege]]"
_organized: true
---

# Quarterly Access Review 2026-10-06

The first completed quarterly access review at Quaylane, the remediation of SOC 2 Type I exception 1 (control AC-04). Run by me with [[kwabena-asare]] and [[colette-fairbanks]], following [[run-the-quarterly-access-review]].

## Scope and Result

Nine systems reviewed: AWS production account (IAM Identity Center), GitHub organization, RDS database roles, the Redis queue console, Pingrove dashboard, the error tracker, the support desk, the HR system, the shared drive security folders.

- 112 access grants reviewed across 21 people and 6 service accounts.
- 7 grants removed: the GitHub account of the summer intern, whose internship had ended, and two former contractors' accounts that should have gone at offboarding, 3 Pingrove dashboard users from customer success who no longer needed it, 1 unused service account with RDS write access.
- 2 grants reduced: production database read access for two engineers moved to the on-call break-glass role.
- Zero grants found for anyone who had left the company more than one business day earlier, apart from the GitHub accounts above, which had no repository access but were still org members.

## Evidence

Signed review sheet per system, exports of the user lists, and tickets for each removal, filed in the [[access-review-log]] and the [[soc2-evidence-folder]]. Summary sent to [[samir-haddad]] on 2026-10-08.

## Notes

It took 3 h 40 min, much of it producing exports. Next review 2027-01-05. The intern and contractor accounts show the offboarding checklist does not cover GitHub org membership for people who never had a laptop; Colette added that step on 2026-10-07.
