---
type: Source
source_type: Documentation
publisher: OWASP Foundation
url: https://cheatsheetseries.owasp.org/cheatsheets/SAML_Security_Cheat_Sheet.html
date_accessed: 2026-10-22
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[sso-integration-design-doc]]"
  - "[[security-and-privacy]]"
_organized: true
---

# SAML Security Cheat Sheet

OWASP Cheat Sheet Series.

## Summary

Practical guidance for implementing SAML safely. It covers transport protection with TLS and signed messages; requiring the protocol elements (request IDs, `InResponseTo`, issuer and recipient) that prevent replay and forgery; validating messages against trusted schemas and verifying signatures with a key obtained from the identity provider rather than one embedded in the message; avoiding XML signature wrapping attacks; short assertion lifetimes and replay detection; and service provider checks on destination, audience, time window and signer, including rejecting SHA-1.

## Why It Matters

Min-jae and Kwabena used it as the review checklist for [[enterprise-sso]] in 2026-04. Two decisions in the [[sso-integration-design-doc]] follow it directly: the signing certificate is pinned at configuration time, and we turned IdP-initiated login off to avoid the relay state and replay issues it describes.

## Key Details

- Pinned IdP key, not the key in the document.
- Short assertion validity and a replay cache.
- Use a maintained library rather than hand-written XML signature handling.

## Caveats

A checklist, not an audit. Ivo Radic's 2026-05 penetration test covered the SSO flow separately.

## Source Links

- [SAML Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/SAML_Security_Cheat_Sheet.html)
