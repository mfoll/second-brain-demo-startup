---
type: Project
status: Completed
start: 2026-01-12
end: 2026-08-28
belongs_to: "[[version-3-release]]"
related_to:
  - "[[appointment-scheduling]]"
  - "[[hamish-pettigrew]]"
has:
  - "[[waitlist-autofill-design-doc]]"
  - "[[how-should-the-waitlist-pick-the-next-patient]]"
  - "[[waitlist-autofill-edge-cases]]"
_organized: true
---

# Waitlist Autofill

When an appointment is cancelled, Quaylane offers the slot by SMS to the first matching person on the clinic's waitlist and the front desk confirms with one click. Before this, front-desk staff phoned down a paper or spreadsheet list.

## Outcome

When an appointment is cancelled, the first matching waitlisted patient is offered the slot by SMS and the front desk confirms with one click. Reached on 2026-08-28 and shipped to everyone in 3.0 on 2026-09-15.

## Current State

- Completed. Enabled by 96 accounts five weeks after GA.
- Beta with 14 clinics from 2026-05-11 to 2026-08-21: 1,140 offers sent, 61% accepted within the 30-minute hold, median time from cancellation to refill 22 minutes. See [[waitlist-autofill-beta-metrics]].
- Known gap: offers go by SMS only. Email offers are in the [[roadmap-2027]] backlog.

## Scope and Boundaries

In scope: matching rules, the SMS offer and its 30-minute hold, front-desk confirmation, an audit trail of who was offered what. Out of scope: patients booking themselves (see [[online-booking-widget]]), any clinical priority. The waitlist never ranks people by anything clinical; clinics may set a manual priority flag, and that is all.

## Working Context

The matching rule was the long argument of the project. Hamish wanted strict first-come order; Felix wanted best fit by preferred times. We settled on first-come among people whose stated availability fits the slot, with the manual flag on top. The reasoning is in [[how-should-the-waitlist-pick-the-next-patient]].

Offers reuse the reminder pipeline and therefore Pingrove. After the [[reminder-outage-2026-03-17]] we put offers on their own queue with a lower priority than reminders, so a burst of cancellations cannot delay reminders. Design in [[waitlist-autofill-design-doc]]; the edge cases that bit us (two cancellations at once, offers crossing midnight, a slot that is rebooked by phone while an offer is out) in [[waitlist-autofill-edge-cases]].

## Next Actions

- [ ] Hand email offers to the 2027 roadmap discussion with a size estimate.

## Important Notes

- [[waitlist-autofill-beta-start-2026-05-11]]
- [[waitlist-autofill-beta-metrics]]
- [[appointment-slot-model]]

## Maintenance Log

- 2026-08-28: Beta closed, feature done.
- 2026-05-11: Beta started with 14 clinics.
- 2026-04-06: Ayesha joined the work.
- 2026-01-12: Started.
