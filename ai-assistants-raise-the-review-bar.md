---
type: Opinion
status: Active
confidence: Low
belongs_to: "[[ai-assisted-development]]"
related_to:
  - "[[should-engineers-use-ai-assistants-on-production-code]]"
  - "[[code-review-and-delivery]]"
_organized: true
---

# AI Assistants Raise The Review Bar

## Stance

Coding assistants move effort from writing code to reading it. If we allow them, review becomes the bottleneck and the quality control, so the reviewer's job gets harder, not easier.

## Scope

Assistant-written code in our production repositories. Not prototypes, scripts or tests run only locally.

## Why I Think This

- In the pilot ([[ai-assistant-pilot-results-2026-09]]), pull requests grew by about 18% and time to first review went up, while the authors reported writing faster.
- [[di-biase-2019-effects-of-change-decomposition-on-code-review]] found reviewers of large, mixed changes report more spurious issues; bigger assistant-written diffs push in that direction.
- [[alaswad-2026-toward-llm-aware-software-effort-estimation]] argues that effort shifts toward validation and integration once assistants write code. That matches what our reviewers said.

## What Would Change My Mind

Six months of data in which assistant-heavy pull requests have the same post-merge fix rate and review time as others. Low confidence: three engineers for seven weeks is a small sample.

## Implications

If we allow assistants, pair it with a soft size limit on pull requests and keep the one-approval rule exactly as it is.
