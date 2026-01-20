---
type: Note
belongs_to: "[[waitlist-autofill]]"
related_to:
  - "[[waitlist-autofill-design-doc]]"
  - "[[appointment-slot-model]]"
_organized: true
---

# Waitlist Autofill Edge Cases

The cases that broke or nearly broke waitlist autofill during development and beta, with what we did. Kept because the same shapes will come back with the booking widget.

1. **Two cancellations within a minute in the same room.** The same person got both offers. Fix: one active offer per waitlist entry (`QL-1543`, 2026-05-14).
2. **Front desk rebooks by phone while an offer is out.** The hold blocks the slot, so the phone booking fails with a confusing error. Fix: the error now says a waitlist offer is pending and offers to cancel it.
3. **Offer accepted after the hold expired.** The link shows "this slot is no longer available" and the person stays on the list. Before the fix they were removed.
4. **Offers at night.** Cancellations at 22:00 for the next morning sent offers at 22:00. Clinics hated it. Offers are now queued until 07:30 local time, and the hold starts when the message is sent.
5. **Slot crosses a roster change.** The staff member's shift ends in the middle of the slot. Matching now checks the full range against the roster, not just the start.
6. **Person on several clinics' waitlists in a group.** Within Meridale, one person may be on lists at two sites. We treat each site's list separately; no cross-site offers.
7. **Pingrove rate limit.** A clinic cancelling a whole day (staff illness) generated 40 offers at once. Offers go through their own lower-priority queue and are spread over several minutes, so reminders are never delayed. Rule added after the [[reminder-outage-2026-03-17]].

Design: [[waitlist-autofill-design-doc]].
