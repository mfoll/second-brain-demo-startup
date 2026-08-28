---
type: Event
date: 2026-08-20
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[olu-ajayi]]"
  - "[[intern-project-brief-2026]]"
  - "[[break-glass-change-log]]"
_organized: true
---

# Intern Demo Day 2026-08-20

[[olu-ajayi|Olu Ajayi]] demonstrated the break-glass watcher to the whole company, 25 minutes on the Thursday all-hands.

## What he showed

- The GitHub Action that runs on every push to `main` in the four production repositories, checks for an approving review, and opens a `QL-` ticket if the merge has none and no row appears in the [[break-glass-change-log]] within two hours.
- A dry run on the history since 2026-04-30: it found all four break-glass merges up to that date and no unlogged bypass.
- What he did not do: it does not block anything, by design; blocking is branch protection's job.

## Reactions

[[colette-fairbanks]] asked for a monthly export for the SOC 2 Type II evidence folder; Olu added it the next day. [[renata-castellano]] asked if we would have an intern again; I said yes if we can supervise properly, which this year depended on [[ayesha-qureshi]]'s time.
