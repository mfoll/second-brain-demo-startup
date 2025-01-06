---
type: Concept
maturity: Seed
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[multi-tenancy]]"
  - "[[database-per-tenant]]"
_organized: true
---

# Noisy Neighbor

In a shared system, one tenant's heavy usage degrades everyone else's experience. It is the cost of sharing that [[row-level-security]] does nothing about.

## Where We See It

- Large clinic groups running a year of appointment exports at 08:30, when front desks open.
- Waitlist autofill for a big tenant scanning many slots after a mass cancellation.
- Before 2026-08, Meridale's onboarding imports were the most likely noisy neighbor. They now run on their own instance.

## What We Do

- Exports and imports go through the job queue with per-tenant concurrency of 2.
- Statement timeout of 15 seconds for API transactions.
- Slow query log tagged with tenant ID so we can see who is noisy.

## Open

Per-tenant rate limits on the API are not built yet. Nobody has asked for them; I expect we will need them when the [[online-booking-widget]] lets patients hit the API directly.
