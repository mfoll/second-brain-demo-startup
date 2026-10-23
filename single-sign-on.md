---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/Single_sign-on
date_accessed: 2026-10-22
last_edited: 2026-10-21
licence: CC BY-SA 4.0
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[security-assertion-markup-language]]"
  - "[[enterprise-readiness]]"
_organized: true
---

# Single sign-on

Wikipedia article, last edited 2026-10-21.

## Summary

Single sign-on is an authentication scheme in which a user logs in once with one identity and gains access to several related but independent software systems. The article covers the benefits (fewer passwords, central control of access) and the trade-off that one compromised identity reaches everything behind it.

## Why It Matters

Background I sent to Renata and Dana in 2026-02 when Meridale's SSO condition turned into a project. For a clinic group, the point of SSO is control: when a front-desk employee leaves, Meridale's IT team disables one account and access to Quaylane goes with it. That is why we built SCIM deprovisioning alongside login ([[scim-deprovisioning]]) and why SSO sits first in [[enterprise-readiness]].

## Caveats

General background only; the protocol we use is SAML ([[security-assertion-markup-language]]).

## Source Links

- [Single sign-on](https://en.wikipedia.org/wiki/Single_sign-on), CC BY-SA 4.0
