---
type: Source
source_type: Internal configuration notes
date_accessed: 2026-06-30
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[samir-haddad]]"
  - "[[meridale-clinic-group]]"
_organized: true
---

# Meridale IdP Configuration Notes

Min-jae Oh's notes on configuring SSO with Meridale's identity provider, Microsoft Entra ID, kept so the next customer setup is faster.

## Summary

- Meridale configured an enterprise application with our SP metadata; Samir Haddad's team owns their side.
- Attributes mapped: email as NameID, given and family name, one group attribute for role.
- SCIM provisioning enabled with a token generated in Quaylane and stored in their tenant.

## Why It Matters

The setup took three sessions with Samir. With these notes, Min-jae estimates about two days per new SSO customer, the number behind [[should-we-charge-separately-for-sso]].

## Key Details

- Pitfall: the identity provider sends email addresses with mixed case; we normalize to lowercase at both login and SCIM.
- Pitfall: the certificate Meridale generated expires after one year. Rotation scheduled with a reminder 30 days before.
- Two roles: `scheduler` and `site_admin`.

## Caveats

No secrets or tenant identifiers are kept in these notes. They live in the secrets manager.

## Source Location

`quaylane-api/docs/runbooks/sso-customer-setup.md`, section "Meridale".
