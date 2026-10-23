---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/System_for_Cross-domain_Identity_Management
date_accessed: 2026-10-22
last_edited: 2026-06-20
licence: CC BY-SA 4.0
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[scim-deprovisioning]]"
  - "[[scim-protocol-rfc-7644]]"
_organized: true
---

# System for Cross-domain Identity Management

Wikipedia article, last edited 2026-06-20.

## Summary

SCIM is an open standard that lets one system tell another about user accounts automatically, so that accounts created, changed or removed in one system (typically a company's identity provider) are reflected in the applications it connects to.

## Why It Matters

The short explanation I give non-engineers for why SSO alone was not enough for Meridale: SSO decides who can log in, SCIM tells us when someone has left. Imani's team uses this article's framing in onboarding calls with enterprise customers. Implementation detail is in [[scim-protocol-rfc-7644]] and our own behavior in [[scim-deprovisioning]].

## Caveats

High-level overview. Identity providers differ in which SCIM operations they send.

## Source Links

- [System for Cross-domain Identity Management](https://en.wikipedia.org/wiki/System_for_Cross-domain_Identity_Management), CC BY-SA 4.0
