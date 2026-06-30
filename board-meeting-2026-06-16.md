---
type: Event
date: 2026-06-16
belongs_to: "[[support-the-company]]"
related_to:
  - "[[margot-ellison]]"
  - "[[architecture-review-2026-06-11]]"
  - "[[release-planning-2026-06-02]]"
_organized: true
---

# Board Meeting 2026-06-16

Quarterly board meeting, the hardest engineering page I have presented. Renata, Margot Ellison, me; Gwen Talbot for the extension item.

## Engineering Page

- The [[reminder-outage-2026-03-17]] and its postmortem: 9 actions, all closed by 2026-05-29.
- Version 3 moved from 2026-06-23 to 2026-09-15 ([[release-planning-2026-06-02]]); SSO split out to ship by 2026-06-30 for Meridale.
- Partial reversal of the tenant isolation decision ([[architecture-review-2026-06-11]]): dedicated databases only for enterprise contracts, row-level security for everyone else. 48 tenants to fold back.
- SOC 2 readiness: 11 gaps found in April, 7 closed.

## Discussion

Margot asked whether the reversal meant the first half of the year was wasted. My answer: the migration tooling built for the pilot is what we use for Meridale's dedicated database; what we stop paying is 2 h 40 min migrations and +$3,100 a month on RDS for clinics that never asked for a database of their own. She asked that the board see the cost of a decision like this before it is made next time, not after. I agreed and now put a cost line in every architecture decision that goes to the board.

## Decisions

- Board accepted the new Version 3 date and the reversal.
- Extension: Renata authorized to negotiate with Copperwell.
- Next meeting 2026-09-22.
