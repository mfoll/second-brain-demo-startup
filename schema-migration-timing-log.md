---
type: Source
source_type: Spreadsheet
date_accessed: 2026-06-08
belongs_to: "[[tenant-isolation-migration]]"
related_to:
  - "[[migration-fan-out]]"
  - "[[run-a-schema-migration]]"
_organized: true
---

# Schema Migration Timing Log

A sheet where every production schema migration gets one row: date, pull request, databases touched, wall-clock duration, failures.

## Key Details

- 2025 median: 6 minutes, one database.
- 2026-02 (13 databases): 19 minutes.
- 2026-05 (49 databases, throttled): median 2 h 40 min; longest 4 h 05 min, for an index build.
- Two migrations in 2026-05 left tenants on mixed schema versions for over an hour after a failure partway through.
- Since 2026-08-28 (two databases): 6 to 12 minutes.

## Source Location

Engineering shared drive, `Platform/schema-migration-log`. Filled in by whoever runs the migration, per [[run-a-schema-migration]].
