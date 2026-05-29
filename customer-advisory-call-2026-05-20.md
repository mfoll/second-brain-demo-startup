---
type: Event
date: 2026-05-20
belongs_to: "[[customer-feedback-loop]]"
related_to:
  - "[[ngaire-tamihana]]"
  - "[[luis-montoya]]"
  - "[[hana-kovarik]]"
_organized: true
---

# Customer Advisory Call 2026-05-20

Twice-yearly call with the informal customer advisory group: six practice and office managers from small and mid-size clinics. Felix chaired; Imani, Mai and I attended. 75 minutes.

## Topics

- **The March outage.** [[hana-kovarik|Hana Kovarik]] asked what had changed. I walked through the postmortem actions from [[postmortem-review-2026-03-24]] in plain terms: a connection pooler, a throttle on migration jobs, an alert when reminders queue for more than ten minutes. She asked for a status page; we added it to the feedback log.
- **Online booking.** [[ngaire-tamihana|Ngaire Tamihana]] and two others want it. One office manager said they would not turn it on. This is where the [[online-booking-widget]] idea started taking shape.
- **Recall reminders.** [[luis-montoya|Luis Montoya]] described how his practices track periodic checkups by hand. Follow-up in [[dental-recall-reminders-request]].
- **Waitlist autofill.** Shown as a demo. Main concern: what happens if the front desk has already rebooked by phone. Answer in [[waitlist-autofill-edge-cases]].

## Follow-up

- All points logged in the [[customer-feedback-log]] tagged `advisory-2026-05`.
- Next call planned for 2026-11-18.
