---
type: Source
source_type: Internal document
date_accessed: 2026-06-08
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[olu-ajayi]]"
  - "[[break-glass-change-log]]"
_organized: true
---

# Intern Project Brief 2026

The one-page brief for [[olu-ajayi]]'s summer internship, 2026-06-08 to 2026-08-21.

## Key Details

- Goal: a GitHub Action that detects merges to `main` without an approving review in the four production repositories and opens a `QL-` ticket if no [[break-glass-change-log]] row appears within two hours.
- Non-goals: blocking merges (branch protection does that); any access to production data.
- Supervisor: [[ayesha-qureshi]]; second contact: Nikolas.
- Milestones: design note by week 2, running in dry-run by week 6, live by week 9, demo in week 11.

## Outcome

Live on 2026-08-04, demo at [[intern-demo-day-2026-08-20]]. Monthly export for SOC 2 evidence added at Colette's request.

## Source Location

Engineering shared drive, `Interns / 2026`; code in `quaylane-infra/tools/break-glass-watcher`.
