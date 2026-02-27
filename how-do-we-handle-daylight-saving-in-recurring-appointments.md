---
type: Question
status: Answered
belongs_to: "[[multi-location-calendars]]"
related_to:
  - "[[postgresql-date-time-types]]"
  - "[[icalendar-rfc-5545]]"
  - "[[appointment-scheduling]]"
_organized: true
---

# How Do We Handle Daylight Saving In Recurring Appointments?

## Question

A weekly appointment booked at 09:00 in winter should still be at 09:00 local time in summer. With multi-location calendars, staff may work at sites in different time zones. How do we store and expand recurring appointments so the wall-clock time holds?

## Current Answer

> [!info]
> Store each occurrence as `timestamptz` and store the series rule with the site's IANA zone name, never a fixed offset. Expand occurrences in the site's zone, then convert to UTC. A staff member's day view is rendered in the zone of the site where each appointment takes place, with a marker when it differs from the viewer's zone.

Agreed in 2026-04 by Lucia and Teodora; implemented in `quaylane-api` as part of [[multi-location-calendars]].

## Why

- The PostgreSQL manual is explicit that `timestamptz` keeps no zone and that full zone names carry daylight-saving rules while abbreviations are fixed offsets; see [[postgresql-date-time-types]].
- Recurrence follows the iCalendar model of a rule plus a time zone reference ([[icalendar-rfc-5545]]). We use a small subset: weekly and every-N-weeks, with an end date or a count.

## History

Before 3.0, series were stored with the account's offset at creation time. Twice a year we got a handful of tickets about appointments one hour off. The backfill to zone names ran on 2026-04-28 over 38,000 active series.

## Open edge

Sites near a zone boundary that run on a neighbor's time informally. Not a real case yet.
