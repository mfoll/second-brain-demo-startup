---
type: Question
status: Open
belongs_to: "[[ai-assisted-development]]"
related_to:
  - "[[ai-coding-tools-policy-draft]]"
  - "[[code-review-policy]]"
  - "[[security-and-privacy]]"
_organized: true
---

# Should Engineers Use AI Assistants On Production Code?

After the 2026-08 to 2026-09 pilot, should coding assistants be allowed on the four production repositories for everyone, and under what rules?

## Current Answer

Leaning yes, with three rules, but not decided: no customer data in prompts or context, ever; generated code goes through the same one-approval rule as any other change; and an agent-opened pull request needs approval from someone other than the person who started the agent. Draft in [[ai-coding-tools-policy-draft]].

## What the pilot showed

From [[ai-assistant-pilot-results-2026-09]]: the three engineers wrote tests faster and liked it for boilerplate; median pull request size grew by about 18%; time to first review went up. My stance on that trade is [[ai-assistants-raise-the-review-bar]].

## Still to settle

- Whether the vendor's data handling is acceptable to Meridale's security team. [[samir-haddad]] has not been asked yet, and the questionnaire answers we gave in 2025 did not mention it.
- Whether this needs a vendor risk entry in the SOC 2 scope; asked [[colette-fairbanks]].
- Whether pull request size needs a soft limit, following [[di-biase-2019-effects-of-change-decomposition-on-code-review]].
