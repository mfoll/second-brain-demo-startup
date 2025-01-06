---
type: Concept
maturity: Growing
belongs_to: "[[partner-with-customers]]"
related_to:
  - "[[appointment-scheduling]]"
  - "[[product-usage-dashboard]]"
_organized: true
---

# No-Show Rate

The share of booked appointments that the front desk marks as "did not attend", computed per account per month. Clinics care about it more than any other number we show them, because empty slots are lost income.

## How we compute it

`no_shows / (attended + no_shows)` over appointments whose start time has passed, excluding appointments cancelled by the clinic. It depends entirely on front-desk staff marking attendance, which about 70% of accounts do consistently. Accounts that never mark attendance show no rate rather than zero.

## What we do not do

We never compute it per patient in anything we show or export, and we never relate it to the type of visit beyond the appointment type name the clinic chose. It is an operational count. That boundary matters for our privacy posture and for the SOC 2 scope.

## Why it matters for the product

- Reminders exist to bring it down. Accounts with SMS reminders on average 4.1% against 7.9% without, in our 2025 data. That is a correlation across very different clinics, not an effect size.
- [[waitlist-autofill]] refills cancellations, which is a different gap; a no-show happens too late to refill.
