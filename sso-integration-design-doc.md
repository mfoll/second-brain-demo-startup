---
type: Source
source_type: Internal design document
date_accessed: 2026-03-16
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[min-jae-oh]]"
  - "[[owasp-saml-security-cheat-sheet]]"
  - "[[scim-deprovisioning]]"
_organized: true
---

# SSO Integration Design Doc

Min-jae Oh's design for SAML SSO and SCIM provisioning, approved on 2026-03-16.

## Summary

- SP-initiated SAML 2.0 only; IdP-initiated login disabled.
- Per-organization IdP metadata, with the signing certificate pinned at configuration time.
- SCIM 2.0 `/Users` endpoint with bearer token per organization; deprovisioning ends sessions immediately.
- A maintained open-source SAML library for XML signature handling.

## Why It Matters

It is the reference for every new SSO customer and for the security answers on SSO in questionnaires. The review checklist used the [[owasp-saml-security-cheat-sheet]].

## Key Details

- Options rejected: a hosted identity service (cost per user and another vendor in the SOC 2 scope), and writing XML signature validation ourselves (the classic source of SAML vulnerabilities).
- Assertions accepted for 5 minutes; replay cache keyed on assertion ID.
- Role mapping: two roles from one IdP group attribute.

## Caveats

OpenID Connect is out of scope. Group sync is minimal.

## Source Location

`quaylane-api/docs/design/sso.md`; review thread in pull request 2304.
