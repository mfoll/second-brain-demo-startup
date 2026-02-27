---
type: Source
source_type: Internal design document
date_accessed: 2026-02-23
belongs_to: "[[waitlist-autofill]]"
related_to:
  - "[[hamish-pettigrew]]"
  - "[[waitlist-autofill-edge-cases]]"
_organized: true
---

# Waitlist Autofill Design Doc

Hamish Pettigrew's design for [[waitlist-autofill]], approved on 2026-02-23 and revised on 2026-04-02 after the March outage.

## Summary

- On cancellation, the matching job finds waitlist entries whose availability fits the freed range, ordered by join time, manual flag first.
- One offer at a time per slot, with a 30-minute hold on the range.
- The SMS contains a link; acceptance converts the hold to an appointment pending front-desk confirmation.

## Why It Matters

The April revision moved offers to their own queue at lower priority than reminders and capped offer throughput per account, so cancellations can never starve reminders or push retries into the Pingrove rate limit. That came straight from the [[reminder-outage-2026-03-17]].

## Key Details

- Tables: `waitlist_entries`, `holds`, `waitlist_offers`.
- Offers are sent between 07:30 and 20:00 site time only.
- Audit: each offer records who was offered, when, and the outcome.

## Caveats

The matching section describes strict first-come; the decision to filter by fit came later and is in [[how-should-the-waitlist-pick-the-next-patient]].

## Source Location

`quaylane-workers/docs/design/waitlist-autofill.md`.
