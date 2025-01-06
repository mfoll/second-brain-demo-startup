---
type: Note
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[roadmap-2027]]"
  - "[[version-3-release-plan]]"
_archived: true
_organized: true
---

# Roadmap 2026 First Draft

> [!warning]
> Archived. Superseded by the [[version-3-release-plan]] of 2026-01-05. Kept to compare what we said in October 2025 with what happened.

Written by Felix and me on 2025-10-20, before the Meridale questionnaire had turned into an architecture decision.

## What it said

- Q1: waitlist autofill.
- Q2: multi-location calendars and online booking pilot.
- Q3: reporting.
- Q4: native calendar sync.
- Platform: "minor database work for enterprise customers", estimated at 3 engineer-weeks.

## What happened instead

- The "minor database work" became the [[tenant-isolation-migration]], about 30 engineer-weeks across 2026.
- SSO and SOC 2 arrived as contract conditions in 2026-01.
- Waitlist and calendars shipped together in 3.0 on 2026-09-15.
- Online booking, reporting and calendar sync did not start.

The lesson is in [[lessons-from-the-version-3-slip]]: we priced platform work as if we knew its size.
