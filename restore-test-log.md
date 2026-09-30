---
type: Source
source_type: Spreadsheet
date_accessed: 2026-09-09
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[primary-postgres-cluster]]"
  - "[[soc2-control-matrix]]"
_organized: true
---

# Restore Test Log

Quarterly record of backup restore tests, kept as SOC 2 evidence for the backup control.

## Key Details

- 2026-03-10: primary, point-in-time restore to scratch instance, 41 minutes, row counts checked on 5 tables.
- 2026-06-09: primary, 37 minutes.
- 2026-09-09: primary and `ent-meridale`, 34 minutes each; first test of a dedicated enterprise database.
- Each test ends with the scratch instance deleted and the deletion logged.

## Source Location

SOC 2 evidence folder, `Backups/restore-tests`, owned by [[kwabena-asare]].
