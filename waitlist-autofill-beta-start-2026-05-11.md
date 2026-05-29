---
type: Event
date: 2026-05-11
belongs_to: "[[waitlist-autofill]]"
related_to:
  - "[[waitlist-autofill-beta-metrics]]"
  - "[[hamish-pettigrew]]"
_organized: true
---

# Waitlist Autofill Beta Start 2026-05-11

Waitlist autofill turned on for 14 beta clinics: 6 physiotherapy, 4 dental, 3 family practice and Joanne Pruett's Meridale pilot clinic.

## Setup

- Flag `waitlist_autofill` enabled per account by Hamish; listed in [[feature-flag-inventory-v3]].
- Offers on their own queue, `waitlist-offers`, at lower priority than reminders, a rule we added after the [[reminder-outage-2026-03-17]].
- Offer hold set to 30 minutes. Clinics could not change it during the beta.
- Daily check by Hamish and Ayesha of offers sent, accepted and expired.

## First week

- 176 offers sent, 98 accepted.
- One bug: when two appointments in the same room were cancelled within a minute, the same person received both offers (`QL-1543`, fixed 2026-05-14). Listed in [[waitlist-autofill-edge-cases]].
- One clinic turned it off on day two because staff had not been told it was on. Imani added a training step to the enablement checklist.

The beta was meant to end in June. It ran to 2026-08-21 after [[release-planning-2026-06-02]].
