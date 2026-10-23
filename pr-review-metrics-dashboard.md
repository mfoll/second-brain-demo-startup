---
type: Source
source_type: Internal dashboard
date_accessed: 2026-10-06
belongs_to: "[[engineering-metrics]]"
related_to:
  - "[[code-review-and-delivery]]"
  - "[[review-rules-should-be-boring]]"
_organized: true
---

# PR Review Metrics Dashboard

A small dashboard built from the GitHub API with a scheduled GitHub Actions job, showing review flow for the four production repositories. Team-level only.

## Key Details (2026-Q3)

- Pull requests merged: 612.
- Median time to first review: 3.1 working hours (2.4 in Q1, before the rule).
- Median time from opening to merge: 1.4 days.
- Approvals given in under two minutes on diffs over 200 lines: 7, which I look at as possible rubber stamps.
- Median pull request size: 142 changed lines.

## Why It Matters

My check on whether the one-approval rule is being followed in spirit ([[review-rules-should-be-boring]]), and the baseline for the AI pilot comparison ([[ai-assistant-pilot-results-2026-09]]).

## Caveats

No per-person views, deliberately. Time to first review counts working hours only, which the job approximates from the author's time zone.

## Source Location

Internal dashboard in the engineering workspace; job code in `quaylane-infra/tools/review-metrics`.
