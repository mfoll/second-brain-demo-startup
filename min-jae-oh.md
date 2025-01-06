---
type: Person
belongs_to: "[[lead-engineering-team]]"
related_to:
  - "[[enterprise-sso]]"
  - "[[sso-integration-design-doc]]"
_organized: true
---

# Min-jae Oh

Engineer, integrations and SSO. Joined in 2024-09.

## Role

Min-jae owns everything that talks to systems outside Quaylane: the Pingrove client for SMS, email delivery, calendar exports and, since 2026-03, identity. He built [[enterprise-sso]] end to end: SAML login, the per-organization IdP settings page and SCIM deprovisioning. He worked directly with [[samir-haddad|Samir Haddad]] at Meridale on their identity provider setup ([[meridale-idp-configuration-notes]]).

## How we work together

- Quiet in meetings and very clear in writing. His design docs are the best on the team; [[sso-integration-design-doc]] is the template I point new engineers to.
- He asks for review early. When SSO had a fixed date, he split the work into eleven small pull requests rather than one big one, which made the SOC 2 review rule painless for him.
- One-to-one every second Wednesday.

## Current threads

- Support for two more SSO customers after GA, see [[should-we-charge-separately-for-sso]].
- Exploring OpenID Connect for 2027; not committed.
- Part of the on-call rotation since the redesign.
