---
type: Source
source_type: Documentation
publisher: Internet Engineering Task Force (RFC Editor)
url: https://www.rfc-editor.org/rfc/rfc5545
date_accessed: 2026-10-22
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[how-do-we-handle-daylight-saving-in-recurring-appointments]]"
  - "[[appointment-scheduling]]"
_organized: true
---

# Internet Calendaring and Scheduling Core Object Specification (iCalendar)

RFC 5545, September 2009, Proposed Standard. Obsoletes RFC 2445.

## Summary

The standard data format for exchanging calendar and scheduling information: events, to-dos, journal entries and free/busy time, independent of any calendar service. Events are `VEVENT` components. Repetition is described by the `RRULE` property with rule parts such as `FREQ` (required), `INTERVAL`, `COUNT` and `UNTIL`. Time values can refer by `TZID` to a `VTIMEZONE` component that defines the zone.

## Why It Matters

Our recurrence model is a deliberately small subset of this one: weekly or every N weeks, ending at a date or after a count, always tied to a zone. Keeping to the RFC's vocabulary means calendar export (the `.ics` feed Min-jae maintains) needs no translation. It informed [[how-do-we-handle-daylight-saving-in-recurring-appointments]].

## Key Details

- Rule plus zone, not a list of precomputed occurrences.
- Every `TZID` used needs a matching `VTIMEZONE` in the object.

## Caveats

The RFC allows far more than we support (monthly by weekday, exceptions lists). Native calendar sync, if we ever build it, would need more of it.

## Source Links

- [RFC 5545](https://www.rfc-editor.org/rfc/rfc5545)
