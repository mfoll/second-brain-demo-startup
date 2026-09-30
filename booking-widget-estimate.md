---
type: Source
source_type: Internal estimate
date_accessed: 2026-09-25
belongs_to: "[[online-booking-widget]]"
related_to:
  - "[[should-the-booking-widget-ship-in-2027]]"
  - "[[malik-2026-hybrid-deep-learning-user-story-effort-estimation]]"
_organized: true
---

# Booking Widget Estimate

My first estimate for the [[online-booking-widget]], dated 2026-09-25, awaiting review by Teodora and Lucia.

## Summary

- Minimal version: one service at one site, bookable slots set by the clinic, SMS and email confirmation, an embed snippet. 14 to 20 engineer-weeks.
- Security work: rate limiting, bot protection, framing rules, a pre-launch penetration test. About 3 engineer-weeks plus the test.
- Support and documentation: about 2 weeks of customer success time before launch.

## Why It Matters

It is the main cost input to [[should-the-booking-widget-ship-in-2027]] and to [[what-should-the-2027-roadmap-cut]].

## Key Details

| Part | Weeks |
| --- | --- |
| Public slot API and holds | 4 to 5 |
| Widget front end and embed | 4 to 6 |
| Clinic settings (what is bookable) | 2 to 3 |
| Confirmations and cancellations | 2 to 3 |
| Testing with beta clinics | 2 to 3 |

The range is wide on purpose. Our estimates for new surfaces have run 30 to 50% over; tenant work ran much more.

## Caveats

Not a commitment. Excludes payments, patient accounts and multi-site booking. A link-based version for returning patients could be about 10 weeks.

## Source Location

Google Docs, `Product/2027/Booking widget estimate`, owned by me.
