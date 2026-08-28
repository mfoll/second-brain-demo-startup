---
type: Source
source_type: Internal design library
date_accessed: 2026-08-03
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[mai-nakagawa]]"
  - "[[usability-testing]]"
_organized: true
---

# Quaylane Design Library

Mai Nakagawa's component library and screen designs in Figma, the source of truth for the look of the web app.

## Summary

- About 120 components mirrored in `quaylane-web/src/components`.
- Calendar grid, site switcher and waitlist screens for 3.0.
- A "patterns" page documenting empty states, confirmations and error messages.

## Why It Matters

Engineering builds from it, and Mai's usability test recordings are linked from each major screen. The site switcher variants she tested with Meridale clinics are kept there.

## Key Details

- Tokens for color and spacing are exported to the web app at each release.
- Accessibility notes per component; keyboard navigation on the calendar is the known gap.

## Caveats

Some 2.x screens are out of date in the library.

## Source Location

Figma, team "Quaylane", file "Quaylane design library", owned by Mai.
