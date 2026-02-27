---
type: Project
status: Completed
start: 2026-02-02
end: 2026-09-04
belongs_to: "[[version-3-release]]"
related_to:
  - "[[lucia-ferreyra]]"
  - "[[meridale-enterprise-rollout]]"
  - "[[appointment-scheduling]]"
has:
  - "[[multi-location-calendars-design-doc]]"
  - "[[calendar-performance-benchmark-2026-07]]"
_organized: true
---

# Multi-Location Calendars

One calendar view across sites for clinic groups, with rooms and staff rosters kept per site. Before 3.0 a clinic group had one Quaylane account per site and a coordinator switched between browser tabs.

## Outcome

One calendar view across sites for clinic groups, with per-site rooms and staff rosters. Reached on 2026-09-04; in 3.0 on 2026-09-15.

## Current State

- Completed. 31 of the 34 accounts with more than one site use the cross-site view.
- Meridale's 42 clinics run as one organization with 42 sites. The largest single view loads in 1.4 s at the 95th percentile after the July work; see [[calendar-performance-benchmark-2026-07]].
- A cross-site room utilization report was cut from 3.0 and sits in [[roadmap-2027]].

## Scope and Boundaries

In scope: organization and site entities, a site filter on every calendar, staff who work at more than one site, per-site opening hours and time zones, and moving an appointment between sites. Out of scope: shared rooms across sites (not a real need) and cross-organization views.

## Working Context

[[lucia-ferreyra|Lucia]] led it, [[mai-nakagawa|Mai]] designed the site switcher after testing three variants with front-desk staff at two Meridale pilot clinics. The data model change was the risky part: every appointment gained a `site_id`, and the backfill ran during the same months as the tenant migration. We ran the backfill as throttled jobs after the [[reminder-outage-2026-03-17]] and it finished on 2026-05-19 without incident.

This was the feature that slipped most. At [[release-planning-2026-06-02]] it was about five weeks behind, mostly because two backend engineers were away on the tenant work. The 95th percentile load time for a 40-site view was 4.8 s in June; Lucia's July work on windowed rendering and a narrower API payload brought it to 1.4 s.

Staff working across sites in different time zones raised the daylight-saving question again; the answer is in [[how-do-we-handle-daylight-saving-in-recurring-appointments]].

## Important Notes

- [[multi-location-calendars-design-doc]]
- [[should-multi-location-calendars-be-enterprise-only]]
- [[joanne-pruett]] for the front-desk view from Meridale.

## Maintenance Log

- 2026-09-04: Done.
- 2026-07-24: Performance target met (under 2 s at p95 for 40 sites).
- 2026-05-19: `site_id` backfill complete.
- 2026-02-02: Started.
