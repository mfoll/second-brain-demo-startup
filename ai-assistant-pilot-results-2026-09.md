---
type: Source
source_type: Internal report
date_accessed: 2026-09-30
belongs_to: "[[ai-assisted-development]]"
related_to:
  - "[[should-engineers-use-ai-assistants-on-production-code]]"
  - "[[ai-assistants-raise-the-review-bar]]"
_organized: true
---

# AI Assistant Pilot Results 2026-09

Write-up of a seven-week pilot (2026-08-03 to 2026-09-25) in which three engineers, [[hamish-pettigrew]], [[ayesha-qureshi]] and [[lucia-ferreyra]], used GitHub Copilot in their editors on `quaylane-web` and `quaylane-api`.

## Summary

Useful for tests, type definitions and repetitive UI code; little help on the scheduling engine. Pull requests got bigger and slower to review. No change in post-merge fix rate that the sample can show.

## Key Details

- Pilot rules: business accounts only; no customer data, logs or production database output in prompts; normal review rules.
- Median pull request size for the three: 168 changed lines, against 142 before (about 18% larger).
- Median time to first review on their pull requests: 3.9 working hours, against 3.1 team-wide.
- Self-reported time saved: "a few hours a week" for two, "about nothing" for one.
- Hamish's note: reviewing assistant-written code is harder because it looks plausible everywhere.

## Caveats

Three people, seven weeks, overlapping with the 3.0 GA crunch. No control group.

## Source Location

Engineering shared drive, `Experiments / 2026-08 coding assistant pilot`.
