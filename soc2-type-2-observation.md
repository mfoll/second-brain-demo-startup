---
type: Project
status: Active
start: 2026-09-01
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[soc2-type-1-audit]]"
  - "[[patrice-ndour]]"
  - "[[meridale-clinic-group]]"
has:
  - "[[soc2-exceptions-remediation-plan]]"
  - "[[type-2-observation-tracker]]"
  - "[[run-the-quarterly-access-review]]"
_organized: true
---

# SOC 2 Type II Observation

The six-month observation window for our first SOC 2 Type II report, 2026-09-01 to 2027-02-28, run by Ashcombe Assurance. The point is to show that the controls in the [[soc2-control-matrix]] operated every time, not only that they existed on one day.

## Outcome

A Type II report from Ashcombe in 2027-04 covering 2026-09-01 to 2027-02-28, with neither of the Type I exceptions repeated.

## Current State

- Window running since 2026-09-01; kickoff notes in [[soc2-type-2-kickoff-2026-09-01]].
- Exception 1 (access review): first quarterly review completed and evidenced on 2026-10-06 ([[quarterly-access-review-2026-10-06]]). Next one due 2027-01-05, inside the window.
- Exception 2 (laptop wipe): MDM remote wipe enforced on all 14 company laptops since 2026-09-08; the device recycler now issues a wipe certificate per serial number. No leaver yet in the window to test it.
- Break-glass changes in the window so far: 1 of the 5 since 2026-04-30 (QL-1702 on 2026-10-02), reviewed within one business day and logged ([[break-glass-change-log]]).
- Ashcombe sampling is expected in 2027-03; Patrice will ask for populations (all PRs merged, all leavers, all new joiners).

## Scope and Boundaries

Same system boundary and criteria as the Type I (Security, Availability, Confidentiality). Expanding to Privacy is deferred until we know whether customers ask for it. Dedicated enterprise databases ([[enterprise-dedicated-databases]]) are in scope from day one of the window.

## Working Context

A Type II is a test of habits. The risk is not a missing control but a missed occurrence: one unreviewed merge, one leaver whose access stays open a week, one quarter without the access review. The [[type-2-observation-tracker]] lists every recurring control with its due dates. [[colette-fairbanks]] checks HR and vendor rows; I check engineering rows on the first Monday of each month.

## Next Actions

- [ ] Run the January access review on 2027-01-05 using [[run-the-quarterly-access-review]].
- [ ] Monthly evidence check with Colette (next 2026-11-02).
- [ ] Confirm the population exports Ashcombe will want (GitHub audit log, HR leaver list) still fit inside retention limits ([[github-organization-audit-log]] keeps 180 days).
- [ ] Book the 2027 penetration test so the report lands before 2027-02-28.
- [ ] Agree Type II fee and sampling dates with Patrice by 2026-12-15.

## Open Questions

- [[do-we-need-iso-27001-as-well-as-soc-2]]
- [[should-we-buy-a-compliance-automation-platform]]

## Important Notes

- [[soc2-exceptions-remediation-plan]]
- [[type-2-observation-tracker]]
- [[soc2-control-matrix]]
- [[control-exception]]

## Do Not Do Yet

> [!danger]
> Do not change the scope, the control wording or the evidence locations in the control matrix during the window without first agreeing it with Patrice Ndour in writing; a mid-window change can split the population and create its own exception.

## Maintenance Log

- 2026-10-06: First quarterly access review evidenced.
- 2026-09-08: MDM remote wipe enforced on all company laptops.
- 2026-09-01: Observation window started.
