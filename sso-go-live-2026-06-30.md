---
type: Event
date: 2026-06-30
belongs_to: "[[enterprise-sso]]"
related_to:
  - "[[min-jae-oh]]"
  - "[[samir-haddad]]"
  - "[[meridale-clinic-group]]"
_organized: true
---

# SSO Go-Live 2026-06-30

Enterprise SSO went live for Meridale on the release train of 2026-06-30, one day before the contract date of 2026-07-01.

## Timeline

- 09:00: Release 2.19.0 deployed with SSO behind the per-organization flag.
- 10:30: Min-jae and Samir Haddad enabled SAML for Meridale's organization. Test logins from the three pilot clinics succeeded.
- 11:15: SCIM provisioning connected; 64 existing pilot users matched by email, 2 left unmatched because of a typo in our records. Fixed by hand.
- 14:00: Samir disabled one test user at Meridale; access removed in Quaylane within 2 minutes, as in [[scim-deprovisioning-test-log]].
- 16:00: Local passwords disabled for the organization.

## Notes

- No incident, no rollback. The only drama was a certificate that Meridale's side had generated with a one-year expiry; Samir agreed to rotate it in 2027-06, and we added a reminder 30 days before.
- Dana sent Victoria Ashdown the confirmation letter the same afternoon.

The condition is tracked in [[meridale-commitments-tracker]]. Feature work recorded in [[enterprise-sso]].
