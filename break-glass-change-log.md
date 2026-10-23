---
type: Source
source_type: Internal spreadsheet
date_accessed: 2026-10-23
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[ship-an-emergency-change]]"
  - "[[soc2-type-2-observation]]"
_organized: true
---

# Break-Glass Change Log

The spreadsheet where every merge to `main` that bypassed the required approval is recorded, with its after-the-fact review. SOC 2 evidence for the change management control.

## Summary

Five rows between 2026-04-30 and 2026-10-23 (QL-1497, QL-1579, QL-1691, QL-1697, QL-1702), all reviewed within one business day. Details in [[ship-an-emergency-change]].

## Key Details

- Columns: date and time of merge, repository, pull request, ticket, reason, merged by, reviewer, review date, follow-up ticket.
- Since 2026-08-04 the watcher from [[intern-project-brief-2026]] opens a ticket when a bypass merge has no row after two hours. It fired once (QL-1697, 2026-08-21, row added that evening).
- Two post-merge reviews produced follow-up tickets: QL-1580 (SAML test coverage) and QL-1692 (row-level security policy tests).

## Why It Matters

Our own record of how often the rule bends. Patrice Ndour's team samples it during the Type II window ([[soc2-type-2-observation]]).

## Source Location

SOC 2 evidence folder, `Change management / break-glass-log`. Write access: the break-glass team and [[colette-fairbanks]]. Not copied into the vault.
