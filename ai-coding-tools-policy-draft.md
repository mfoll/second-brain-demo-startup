---
type: Source
source_type: Internal document
date_accessed: 2026-10-06
belongs_to: "[[ai-assisted-development]]"
related_to:
  - "[[should-engineers-use-ai-assistants-on-production-code]]"
  - "[[security-and-privacy]]"
_organized: true
---

# AI Coding Tools Policy Draft

Draft policy, version 0.3, written 2026-10-06. Not adopted.

## Key Details

1. Allowed tools: those on the approved vendor list with a business agreement that excludes training on our code.
2. Never put customer data, production logs, database output or credentials into a prompt or the tool's context.
3. Generated code is reviewed exactly like other code; the one-approval rule applies unchanged ([[code-review-policy]]).
4. A pull request opened by an agent needs approval from someone other than the person who started the agent. This matches GitHub's own behavior ([[github-docs-approving-a-pull-request-with-required-reviews]]).
5. Say in the pull request description when most of a change was generated.

## Open points

Vendor risk entry for the SOC 2 scope; whether Meridale's security team needs to be told; a soft pull request size limit.

## Source Location

Engineering handbook, `Policies / drafts / ai-coding-tools`.
