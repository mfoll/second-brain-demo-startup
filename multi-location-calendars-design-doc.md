---
type: Source
source_type: Internal design document
date_accessed: 2026-02-16
belongs_to: "[[multi-location-calendars]]"
related_to:
  - "[[lucia-ferreyra]]"
  - "[[appointment-slot-model]]"
_organized: true
---

# Multi-Location Calendars Design Doc

Lucia Ferreyra's design document for [[multi-location-calendars]], approved on 2026-02-16 after review by Teodora, Mai and me.

## Summary

- Introduces `sites` under `organizations`; every room, roster entry and appointment gets a `site_id`.
- Staff can belong to several sites; rosters are per site.
- The calendar gets a site filter and a cross-site view; times display in the site's zone.
- Backfill: every existing account gets one default site, filled by background job.

## Why It Matters

It is the reference for the biggest data model change since 2023. The backfill section was rewritten after the [[reminder-outage-2026-03-17]] to run as throttled jobs, which is why it finished quietly on 2026-05-19.

## Key Details

- Rejected: one Quaylane account per site with a "group" overlay. Simpler at first, but every report and permission would need cross-account joins.
- Rejected: shared rooms across sites. No customer had the case.
- Performance target: under 2 s at p95 for a 40-site week view. Met in July, see [[calendar-performance-benchmark-2026-07]].

## Caveats

The API section is out of date after the July payload changes; the code is the reference.

## Source Location

`quaylane-web/docs/design/multi-location-calendars.md`, with the review thread on pull request 2210.
