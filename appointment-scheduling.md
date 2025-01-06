---
type: Topic
related_to:
  - "[[deliver-the-product]]"
  - "[[appointment-slot-model]]"
  - "[[scheduling-domain-glossary]]"
_organized: true
---

# Appointment Scheduling

The domain Quaylane lives in: how clinic front desks book appointments against rooms, staff rosters and opening hours, how reminders and the waitlist fill gaps, and how all of that behaves across time zones and sites. Use this Topic to find the domain model, the hard edge cases and the reading behind them.

## Core notes

- [[appointment-slot-model]]: slots, resources and holds, and why a booking needs a room and a staff member at the same time.
- [[scheduling-domain-glossary]]: the words clinic staff use and what they mean in our tables.
- [[scheduling-engine-overview]]: the internal design document for the engine in `quaylane-api`. Only Teodora and I knew it well until the 2026 diligence pushed us to fix that.
- [[no-show-rate]]: how we count missed appointments without touching anything clinical.

## Features built on it

- [[waitlist-autofill]] and [[waitlist-autofill-edge-cases]].
- [[multi-location-calendars]] and [[multi-location-calendars-design-doc]].
- [[online-booking-widget]], still an idea.

## Questions and decisions

- [[how-should-the-waitlist-pick-the-next-patient]]
- [[how-do-we-handle-daylight-saving-in-recurring-appointments]]
- [[postgresql-range-types]] is the documentation behind our overlap constraint; [[postgresql-date-time-types]] behind our time zone handling; [[icalendar-rfc-5545]] behind recurrence.

## Related

Reminders themselves are part of the platform story because of the 2026-03-17 outage; see [[reliability-and-incidents]].
