---
type: Question
status: Open
belongs_to: "[[on-call-rotation-redesign]]"
related_to:
  - "[[alert-fatigue]]"
  - "[[paging-report-2026-q3]]"
  - "[[team-health]]"
_organized: true
---

# How Many Pages A Week Is Too Many?

What paging load can six engineers sustain without the rotation wearing people down? I need a number to make the platform hire decision honest rather than a feeling.

## Current Answer

Working threshold: above 8 pages a week across the rotation, or above 3 out-of-hours pages a week, the load is too high to leave to rotation alone. Q3 2026 was about 9 and about 3 ([[paging-report-2026-q3]]), so we sit right at the line.

## Inputs

- Our own history: 14.5 a week in the first weeks of the rotation ([[on-call-review-2026-05-15]]), about 9 in Q3.
- [[kwabena-asare]] wants it under 6.
- Leon's warning at [[founders-circle-2026-09-10]]: two engineers burned out before they hired a platform engineer.
- Rohan's view: 3 out-of-hours pages a week is manageable for six people, not for three ([[platform-engineer-conversation-2026-10-07]]).
- The survey score on on-call sustainability, 3.5 of 5 in June ([[team-health-survey-2026-06]]).

## Why still open

A page count says nothing about how bad each page is. A five-minute queue-age blip at 02:00 and a two-hour database incident count the same. I want time-to-resolve and sleep-interrupting pages in the Q4 report before committing to a threshold. Feeds [[should-we-hire-a-platform-engineer-or-keep-everyone-on-call]].
