---
type: Source
source_type: Scientific paper
url: https://doi.org/10.7717/peerj-cs.193
doi: 10.7717/peerj-cs.193
pmid: "33816846"
date_accessed: 2026-04-06
licence: CC BY
belongs_to: "[[code-review-policy]]"
related_to:
  - "[[code-review]]"
  - "[[code-review-and-delivery]]"
_organized: true
---

# The effects of change decomposition on code review-a controlled experiment.

di Biase M, Bruntink M, van Deursen A, Bacchelli A. PeerJ Computer Science, 2019.

## Summary

A controlled experiment with 28 developers (professionals and graduate students) reviewing the same change either as one large pull request or decomposed into smaller coherent ones. Decomposed changes led to fewer wrongly reported issues and more context-seeking during review, but did not change the number of real defects found or how well reviewers understood the change's rationale. The authors recommend separating commits that belong to different concepts.

## Why It Matters

I read it while writing the [[code-review-policy]], to check whether a size limit belonged in the rule. Conclusion: no, it belongs in the working agreements as advice ([[team-working-agreements]]), because the effect is on noise and reviewer effort, not on defects caught. It came back in the AI pilot discussion, where pull requests grew ([[ai-assistants-raise-the-review-bar]]).

## Caveats

28 participants, one experimental task. Says nothing about pair programming, so it does not settle Hamish's argument either way.

## Source Links

- [DOI 10.7717/peerj-cs.193](https://doi.org/10.7717/peerj-cs.193), PMID 33816846, PMCID PMC7924728
