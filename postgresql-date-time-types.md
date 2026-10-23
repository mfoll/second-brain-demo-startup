---
type: Source
source_type: Documentation
publisher: The PostgreSQL Global Development Group
url: https://www.postgresql.org/docs/16/datatype-datetime.html
date_accessed: 2026-10-22
belongs_to: "[[multi-location-calendars]]"
related_to:
  - "[[how-do-we-handle-daylight-saving-in-recurring-appointments]]"
  - "[[appointment-scheduling]]"
_organized: true
---

# PostgreSQL 16 Documentation: 8.5. Date/Time Types

## Summary

The PostgreSQL 16 manual section on date and time types. For `timestamp with time zone`, input is converted to UTC and stored as UTC; the original zone is not kept, and output is converted to the session's `TimeZone`. The manual advises full zone names (such as `America/New_York`) over abbreviations, because a full name applies daylight-saving rules for the date in question while an abbreviation is a fixed offset. It discourages `time with time zone`, since an offset without a date has no clear meaning.

## Why It Matters

It is the reference for the answer in [[how-do-we-handle-daylight-saving-in-recurring-appointments]]: store occurrences as `timestamptz`, store the series rule with the site's IANA zone name, expand in that zone. Lucia and Teodora worked from this page when [[multi-location-calendars]] put staff in sites with different zones.

## Key Details

- No zone is retained in `timestamptz`; the site's zone must be stored separately.
- `AT TIME ZONE` converts for display in another zone.

## Caveats

The manual describes the database's behavior; the recurrence logic is ours.

## Source Links

- [PostgreSQL 16: Date/Time Types](https://www.postgresql.org/docs/16/datatype-datetime.html)
