---
type: Source
source_type: Internal spreadsheet
date_accessed: 2026-09-08
belongs_to: "[[secure-and-comply]]"
related_to:
  - "[[soc2-exceptions-remediation-plan]]"
  - "[[colette-fairbanks]]"
_organized: true
---

# Device Inventory

The list of company laptops, kept by [[colette-fairbanks]] and exported from the MDM tool since 2026-09-08.

## Contents

- 14 laptops in use, 2 spares. Per device: serial number, assigned person, MDM enrollment date, disk encryption status, OS version, last check-in.
- All 16 enrolled and encrypted on 2026-09-08. Remote wipe policy enabled.
- Retired devices: serial, date returned, wipe method, recycler certificate reference.

## Why It Exists

Type I exception 2 (a returned laptop with no wipe record). The inventory plus the recycler's per-serial certificate is the evidence for control HR-07 during the Type II.

## Source Location

MDM console export, monthly copy in the [[soc2-evidence-folder]] under `Controls/HR-07/`.
