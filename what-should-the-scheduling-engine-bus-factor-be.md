---
type: Question
status: Open
belongs_to: "[[seed-extension-diligence]]"
related_to:
  - "[[bus-factor]]"
  - "[[teodora-vasilescu]]"
  - "[[technical-diligence-call-2026-08-19]]"
_organized: true
---

# What Should The Scheduling Engine Bus Factor Be?

How many engineers should be able to change the scheduling engine safely, and by when? Raised by [[arun-velayudhan]] in diligence on 2026-08-19, when the honest answer was two: [[teodora-vasilescu]] and me.

## Why It Matters

The engine resolves appointments against rooms, staff rosters and clinic rules; most customer-visible bugs that matter end up there. With two people, a holiday plus an illness stops changes to the core of the product. It is also a hiring and onboarding question: Ayesha and Bram joined in 2026 and neither had touched it.

## Current Answer

Working target: four engineers able to make and review a non-trivial change by 2027-03-31, measured by each having merged and reviewed at least one engine change on their own.

- Recorded walkthrough by Teodora, 2026-09-09, 2 h 10 min.
- Pairing rotation since 2026-09-14: two weeks at a time with Teodora or me. [[ayesha-qureshi]] done (2026-09-14 to 09-25), [[lucia-ferreyra]] in progress.

## What Is Still Open

- Is four the right number for a team of eight, or should it be everyone who goes on call?
- Does the [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]] decision change who should learn it first?
- What to tell Arun before close: progress so far, not a promise of the target.
