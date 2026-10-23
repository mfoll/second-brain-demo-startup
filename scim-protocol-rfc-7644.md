---
type: Source
source_type: Documentation
publisher: Internet Engineering Task Force (RFC Editor)
url: https://www.rfc-editor.org/rfc/rfc7644
date_accessed: 2026-10-22
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[scim-deprovisioning]]"
  - "[[scim-deprovisioning-test-log]]"
_organized: true
---

# System for Cross-domain Identity Management: Protocol

RFC 7644, September 2015, Proposed Standard.

## Summary

The HTTP protocol for provisioning and managing identities across domains. Resources such as `/Users` and `/Groups` are managed with `GET`, `POST`, `PUT`, `PATCH` and `DELETE`. `PATCH` applies partial changes with add, remove and replace operations. Queries support filtering, sorting and pagination. After a `DELETE`, later requests for the resource return 404 and it disappears from query results.

## Why It Matters

Our SCIM endpoint for [[enterprise-sso]] implements the `/Users` part of this protocol. Deprovisioning arrives either as a `DELETE` or as a `PATCH` that marks the user inactive, depending on the customer's identity provider; we handle both the same way ([[scim-deprovisioning]]).

## Key Details

- We implement `/Users` only; `/Groups` is not supported in 2026.
- Filtering on `userName eq` is the one query identity providers actually send us.

## Caveats

The user schema itself, including the `active` attribute, is defined in the companion core schema RFC, not here.

## Source Links

- [RFC 7644](https://www.rfc-editor.org/rfc/rfc7644)
