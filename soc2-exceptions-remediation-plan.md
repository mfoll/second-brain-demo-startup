---
type: Note
belongs_to: "[[soc2-type-2-observation]]"
related_to:
  - "[[soc2-type-1-report]]"
  - "[[control-exception]]"
  - "[[colette-fairbanks]]"
_organized: true
---

# SOC 2 Exceptions Remediation Plan

How we fix the two exceptions in the [[soc2-type-1-report]] and prove the fix during the Type II window. Written by me and [[colette-fairbanks]] on 2026-08-31, sent to [[samir-haddad]] on 2026-09-04.

## Exception 1: Quarterly Access Review (AC-04)

**Finding:** no completed, evidenced access review as of 2026-07-31.

**Root cause:** the review was designed in May and assigned to me, with no calendar entry, no template and no named reviewer per system. It slipped behind fieldwork preparation.

**Fix:**
- Written procedure with a reviewer per system and a fixed agenda ([[run-the-quarterly-access-review]]).
- Fixed dates: first Tuesday of January, April, July and October. Calendar invites to all reviewers through 2027.
- First review completed 2026-10-06 ([[quarterly-access-review-2026-10-06]]), 7 grants removed, evidence in the [[access-review-log]].

**Status:** remediated; must repeat on 2027-01-05 inside the window.

## Exception 2: Laptop Wipe Record (HR-07)

**Finding:** one leaver in 2026-06 returned a laptop, but there was no record that it was wiped before reuse.

**Root cause:** the offboarding checklist said "collect laptop" with no wipe step; the laptop was wiped by whoever reissued it, with no record.

**Fix:**
- MDM enrolled on all 14 company laptops, remote wipe enforced since 2026-09-08 ([[device-inventory]]).
- Checklist step: wipe via MDM on the last day, screenshot of the wipe status filed in the HR system.
- Devices leaving the company go to the recycler, who issues a wipe certificate per serial number.
- GitHub org membership removal added on 2026-10-07 after the access review found stale accounts.

**Status:** fix in place; no leaver yet in the window to test it.

## Watch

Both exceptions were recurring or per-event controls. The [[type-2-observation-tracker]] now lists every such control with its next due date.
