---
type: Project
status: Completed
start: 2026-03-02
end: 2026-06-30
belongs_to: "[[version-3-release]]"
related_to:
  - "[[min-jae-oh]]"
  - "[[meridale-clinic-group]]"
  - "[[security-and-privacy]]"
has:
  - "[[sso-integration-design-doc]]"
  - "[[sso-go-live-2026-06-30]]"
  - "[[scim-deprovisioning]]"
_organized: true
---

# Enterprise SSO

SAML single sign-on and SCIM deprovisioning, built because the Meridale contract required SSO by 2026-07-01. It started inside version 3 and shipped on its own when 3.0 slipped.

## Outcome

SAML single sign-on and SCIM deprovisioning live for Meridale before the 2026-07-01 contract date. Reached on 2026-06-30.

## Current State

- Completed. Meridale's admin users sign in through their identity provider: 288 active users in the 19 live clinics, about 640 expected at full rollout. Local passwords are disabled for their organization.
- SCIM deprovisioning removes access within about two minutes of a user being disabled at Meridale. Tested in [[scim-deprovisioning-test-log]].
- Two other accounts asked for SSO after GA. It is included in the enterprise plan; see [[should-we-charge-separately-for-sso]].

## Scope and Boundaries

In scope: SP-initiated SAML 2.0, per-organization IdP configuration, SCIM 2.0 user provisioning and deprovisioning, an admin setting that disables passwords. Out of scope for 2026: OpenID Connect, group-to-role mapping beyond two roles, IdP-initiated login (we turned it off on purpose, following [[owasp-saml-security-cheat-sheet]]).

## Working Context

[[min-jae-oh|Min-jae Oh]] built it with [[kwabena-asare|Kwabena]] on certificates and secrets. We chose a maintained SAML library over writing XML signature handling ourselves; the reasons and the rejected hosted-auth option are in [[sso-integration-design-doc]]. [[samir-haddad|Samir Haddad]] at Meridale ran their side and the configuration notes are in [[meridale-idp-configuration-notes]].

SSO was also a SOC 2 talking point: deprovisioning through SCIM gave us a clean answer to the offboarding questions in the [[meridale-security-questionnaire]].

When version 3 slipped, [[release-planning-2026-06-02]] split SSO out to ship by 2026-06-30. It shipped behind a per-organization flag on the train of 2026-06-30, see [[sso-go-live-2026-06-30]].

## Important Notes

- [[sso-integration-design-doc]]
- [[scim-deprovisioning]]
- [[single-sign-on]] and [[security-assertion-markup-language]] for background.
- [[scim-protocol-rfc-7644]]

## Maintenance Log

- 2026-06-30: Live for Meridale.
- 2026-06-02: Split out of 3.0 with a fixed date.
- 2026-04-22: First successful login against Meridale's test tenant.
- 2026-03-02: Started.
