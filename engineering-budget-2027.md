---
type: Project
status: Active
start: 2026-10-05
belongs_to: "[[support-the-company]]"
related_to:
  - "[[renata-castellano]]"
  - "[[platform-engineer-hire]]"
  - "[[roadmap-2027]]"
has:
  - "[[engineering-budget-2027-draft]]"
  - "[[cloud-cost-per-clinic-model]]"
  - "[[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]"
  - "[[how-much-should-we-spend-on-security-in-2027]]"
_organized: true
---

# Engineering Budget 2027

The 2027 engineering budget: headcount, cloud, tooling, audit and security costs, agreed with [[renata-castellano]] and presented at the 2026-12-08 board meeting.

## Outcome

A budget Renata accepts by 2026-11-27 and the board approves on 2026-12-08, with the first 2027 hire decided.

## Current State

- Kickoff with Renata on 2026-10-05. Draft due to her on 2026-11-13 so it can go into the board deck.
- Working draft in [[engineering-budget-2027-draft]]: engineering headcount from 8 to 10 (the two hires the extension funds), cloud about $62,000 for the year, audit and security about $71,000, tooling about $29,000.
- The first hire is still open: platform engineer ([[kwabena-asare]]'s case) or a second product engineer ([[felix-ostrowski]]'s case). The draft carries both scenarios; the cost difference is small, the difference in what we can ship is not ([[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]).
- Cloud forecast is driven by [[cloud-cost-per-clinic-model]]: $14 per clinic per month in July 2026, plus dedicated databases for each enterprise contract.

## Scope and Boundaries

Engineering costs only. Salaries are entered as level bands from the [[career-ladder]] rather than individual figures, and this note never records anyone's pay. Sales, customer success and office costs belong to Renata's company budget.

## Working Context

The 2026 budget ([[engineering-budget-2026]]) underestimated two things: the RDS bill during the per-tenant migration (+$3,100 a month at the peak) and compliance (we had not planned on SOC 2 at all in 2025). For 2027 I am budgeting the Type II renewal, a pen test and the on-call stipend explicitly, and keeping a 10% cloud contingency for a second enterprise tenant.

## Next Actions

- [ ] Finish both hiring scenarios with the Q4 paging data by 2026-11-13.
- [ ] Get [[colette-fairbanks]] to confirm audit and vendor lines.
- [ ] Agree the security line ([[how-much-should-we-spend-on-security-in-2027]]).
- [ ] Write the board page; review it with Renata on 2026-11-27.

## Open Questions

- [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]]
- [[how-much-should-we-spend-on-security-in-2027]]
- [[should-we-buy-a-compliance-automation-platform]]

## Important Notes

- [[engineering-budget-2027-draft]]
- [[cloud-cost-per-clinic-model]]
- [[engineering-budget-2026]]
- [[platform-engineer-hire]]

## Maintenance Log

- 2026-10-05: Kickoff with Renata; draft date and scenarios agreed.
