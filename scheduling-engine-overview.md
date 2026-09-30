---
type: Source
source_type: Internal design document
date_accessed: 2026-09-02
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[appointment-slot-model]]"
  - "[[teodora-vasilescu]]"
  - "[[technical-diligence-call-2026-08-19]]"
_organized: true
---

# Scheduling Engine Overview

Internal design document for the scheduling engine in `quaylane-api`: availability calculation, overlap enforcement, holds and recurrence. Originally written by Nadia Carvalho in 2023, rewritten by Teodora Vasilescu and me in 2026-09.

## Summary

- Availability is computed on request from site hours, roster entries, existing appointments and holds; nothing is precomputed except a per-day cache invalidated on any write.
- Overlaps are blocked twice: in code for a friendly message and by exclusion constraints on `tstzrange` columns as the backstop ([[postgresql-range-types]]).
- Recurrence is a weekly or every-N-weeks rule stored with an IANA zone, expanded in the site's zone ([[how-do-we-handle-daylight-saving-in-recurring-appointments]]).

## Why It Matters

Until 2026-09 only Teodora and I understood this code well. Arun Velayudhan called it out as a bus factor risk at the [[technical-diligence-call-2026-08-19]]. The rewrite of this document and a recorded walkthrough were the first two follow-ups; a pairing rotation on the engine started on 2026-09-14, with Ayesha first ([[pairing-rotation-scheduling-engine]]).

## Key Details

- Main modules: `availability/`, `booking/`, `holds/`, `recurrence/`.
- Performance budget: availability for one staff member over 14 days under 80 ms at p95.
- Known debt: the per-day cache is keyed by site, so a roster change at a multi-site staff member invalidates every site they work at.

## Caveats

The walkthrough recording explains intent better than the document. Read both.

## Source Location

- `quaylane-api/docs/scheduling-engine.md` in the repository.
- Walkthrough recording (2026-09-09, 2 h 10 min in four parts) in the engineering shared drive, `Engineering/Recordings/`.
