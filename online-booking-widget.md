---
type: Project
status: Idea
start: 2026-08-10
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[product-discovery]]"
  - "[[roadmap-2027]]"
  - "[[appointment-scheduling]]"
has:
  - "[[booking-widget-discovery-interviews]]"
  - "[[booking-widget-estimate]]"
  - "[[should-the-booking-widget-ship-in-2027]]"
_organized: true
---

# Online Booking Widget

Letting patients book from a clinic's own website through an embeddable Quaylane widget. It is the most requested item in the feedback log and the reason at least four clinics gave for leaving in 2025. It is also a different product with a different user, which is why it is still an Idea.

## Outcome

A go or no-go on letting patients book from a clinic's own website, with a scoped estimate.

## Current State

- Idea. No code. Discovery by Felix and Mai: twelve interviews with practice managers and front-desk leads, summarized in [[booking-widget-discovery-interviews]].
- First estimate in [[booking-widget-estimate]]: 14 to 20 engineer-weeks for a version that books a single service at a single site, plus about 3 weeks of security work.
- Decision expected with the [[roadmap-2027]] in December.

## Scope and Boundaries

The idea covers the public booking flow, an embed snippet for clinic websites, rules for which slots are bookable online, and confirmation by SMS and email. It does not include payments, patient accounts or intake forms. Quaylane does not store anything clinical, and the widget must not change that: no free-text reason for visit.

## Working Context

The pull is clear: online booking appears in 212 feedback items since 2025-03 and in four of the churn reasons in [[churn-analysis-2025]], including [[ezra-feldman|Ezra Feldman]]'s clinic. Practice managers like [[ngaire-tamihana|Ngaire Tamihana]] want it; front-desk leads like [[joanne-pruett|Joanne Pruett]] worry about patients grabbing slots the front desk was holding.

The cost is not only engineering. A public, unauthenticated surface changes our security posture: abuse and bot bookings, framing on third-party sites (see [[owasp-clickjacking-defense-cheat-sheet]]), and a new data flow for the SOC 2 scope. My stance is in [[booking-widget-is-a-different-product]].

## Next Actions

- [ ] Finish the estimate review with Teodora and Lucia.
- [ ] Ask Ivo Radic for a rough price on a pre-launch test of a public booking surface.
- [ ] Bring a go or no-go recommendation to the 2026-11-17 leadership meeting.

## Open Questions

- [[should-the-booking-widget-ship-in-2027]]

## Do Not Do Yet

> [!danger]
> No prototype on production infrastructure and no promise to any customer, Meridale included, until the go or no-go decision is made.

## Maintenance Log

- 2026-09-25: Interviews done; estimate drafted.
- 2026-08-10: Opened as an Idea after the 2026-07 product review.
