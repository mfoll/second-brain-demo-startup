---
type: Source
source_type: Folder pointer
storage_system: Company shared drive
root_key: quaylane_shared_drive
relative_path: Security/SOC2/Evidence
access: guarded-write
last_checked: 2026-10-07
date_accessed: 2026-10-07
belongs_to: "[[soc2-type-2-observation]]"
related_to:
  - "[[soc2-control-matrix]]"
  - "[[colette-fairbanks]]"
_organized: true
---

# SOC 2 Evidence Folder

The governed folder where every piece of SOC 2 evidence lands: exports, signed review sheets, policies with approval records, reports. This note points to it; nothing from it is copied into the vault.

## Structure

- `Controls/<control-id>/<YYYY-MM>/` for recurring evidence, one folder per control in the [[soc2-control-matrix]].
- `AccessReviews/<YYYY-Qn>/` for [[run-the-quarterly-access-review]].
- `Reports/2026-Type1/` for the [[soc2-type-1-report]] and management letter.
- `Requests/2026-Type1/` for Ashcombe's 64 fieldwork requests and our responses.
- `Policies/` for approved policy versions.

## Rules

- Write access: Nikolas, Colette, Kwabena. Read access: Renata and Ashcombe's auditors through a shared link that expires after each fieldwork.
- Nothing with patient data, ever. Exports from production systems list staff accounts and roles only.
- HR evidence (background check confirmations, wipe certificates) stays in the HR system; this folder holds a reference to the record, not the record.

## Why It Matters

During the Type II window the folder is the product. A control without its monthly subfolder is an exception waiting to be found.

## Source Location

Company shared drive, root key `quaylane_shared_drive`, path `Security/SOC2/Evidence`. Guarded write: change structure only with Colette and after telling [[patrice-ndour]].
