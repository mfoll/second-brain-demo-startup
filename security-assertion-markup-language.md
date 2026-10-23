---
type: Source
source_type: Encyclopedia article
url: https://en.wikipedia.org/wiki/SAML
date_accessed: 2026-10-22
last_edited: 2026-10-12
licence: CC BY-SA 4.0
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[single-sign-on]]"
  - "[[sso-integration-design-doc]]"
_organized: true
---

# SAML

Wikipedia article on Security Assertion Markup Language, last edited 2026-10-12.

## Summary

SAML is an open, XML-based standard for exchanging authentication and authorization data between an identity provider and a service provider. Besides the assertion language, it defines protocol messages, bindings that carry them over transports such as HTTP, and profiles that combine these for uses like web browser single sign-on.

## Why It Matters

SAML 2.0 is what Meridale's identity provider speaks, so it is what [[enterprise-sso]] implements. Min-jae used this article to brief the team before the design review; the vocabulary (identity provider, service provider, assertion, binding) is what the [[sso-integration-design-doc]] uses. The security checklist came from the [[owasp-saml-security-cheat-sheet]].

## Caveats

An overview; implementation details come from the specification and the library we use.

## Source Links

- [SAML](https://en.wikipedia.org/wiki/SAML), CC BY-SA 4.0
