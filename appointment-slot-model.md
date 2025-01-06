---
type: Concept
maturity: Evergreen
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[appointment-scheduling]]"
  - "[[scheduling-engine-overview]]"
  - "[[postgresql-range-types]]"
_organized: true
---

# Appointment Slot Model

How Quaylane represents bookable time. Every appointment occupies a time range on two resources at once, a room and a staff member, inside a site's opening hours. A slot is not a stored row; it is what remains free after those constraints are applied.

## The parts

- **Resource**: a room or a staff member, always attached to a site. Equipment is modeled as a room with no walls, which is ugly and works.
- **Availability**: opening hours per site and roster entries per staff member, both as weekly patterns with exceptions.
- **Appointment**: a `tstzrange` on one room and one staff member, with a type that sets its default length.
- **Hold**: a temporary claim on a range, used by [[waitlist-autofill]] offers (30 minutes) and, if it ever exists, the [[online-booking-widget]] checkout.

## The invariant

No two appointments or holds may overlap on the same room or the same staff member. We enforce it in the database, not only in code, with exclusion constraints of the kind the PostgreSQL manual describes for room reservations ([[postgresql-range-types]]). Code checks first so the user gets a friendly message; the constraint is the backstop for races.

## What it does not handle

- Group bookings: several people in one room slot. [[ngaire-tamihana|Ngaire Tamihana]]'s request. It needs a capacity on the appointment and breaks the simple overlap rule.
- Resources shared across sites.

Origin: designed by Nadia Carvalho in 2023, extended for sites in 2026. Detail in [[scheduling-engine-overview]].
