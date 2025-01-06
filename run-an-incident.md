---
type: Procedure
belongs_to: "[[run-the-platform]]"
related_to:
  - "[[reliability-and-incidents]]"
  - "[[on-call-handbook]]"
  - "[[reminder-outage-postmortem]]"
_organized: true
---

# Run An Incident

How Quaylane runs a production incident from the first page to the handoff to a postmortem. Written by Kwabena Asare and me after the [[reminder-outage-2026-03-17]]; adopted on 2026-04-15. Who is on call and how paging works is in [[on-call-handbook]].

## When to Use

Any time clinics cannot use Quaylane as expected: the app is down or erroring, reminders are late or not sent, data looks wrong for a clinic, or a security event is suspected. If in doubt, declare. Downgrading is free; a late declaration is not.

## Severity Levels

| Level | Meaning | Examples |
|---|---|---|
| SEV1 | Many clinics cannot work, or reminders are failing broadly, or a suspected data exposure | 2026-03-17; any cross-tenant data report |
| SEV2 | One feature broken for many clinics, or one clinic cannot work | Waitlist offers not sending; SSO login failing for Meridale |
| SEV3 | Degraded but workable; no customer-visible data issue | Slow calendar loads at peak |

SEV1 and SEV2 always get the full role set and a postmortem. SEV3 gets a commander and a short write-up in the [[incident-log]].

## Roles

- **Incident commander.** Owns decisions and the clock. Does not debug. Defaults to [[kwabena-asare]]; otherwise the primary on-call engineer until handed over. Founders do not take this role ([[incident-commander-should-not-be-the-founder]]).
- **Communications.** A customer success person, normally [[pablo-arriaga]] or [[imani-brooks]]. Owns the status page and clinic updates.
- **Scribe.** Anyone not debugging. Keeps the timeline in the incident channel with timestamps. Never the person also answering executives.
- **Responders.** Engineers the commander pulls in. They report to the commander, not to each other.

## Steps

1. **Declare.** In the incidents channel: `/incident declare SEV? short description`. This opens a channel and a timeline document.
2. **Assign roles** within 5 minutes. The commander names them in the channel, even if the same person must hold two for a while.
3. **Stabilize before diagnosing.** Stop the bleeding first: halt migrations and batch jobs, scale workers down, roll back the last deploy. Emergency fixes follow [[ship-an-emergency-change]].
4. **Communicate.** First status page post within 15 minutes of declaring. Then a clinic update every 30 minutes until resolved, even if nothing changed. Templates live in the customer success drive (postmortem action 7).
5. **Name affected tenants.** Use counts and tenant IDs in the channel, never patient-level details.
6. **Resolve.** The commander declares resolved when the customer-facing symptom is gone for 30 minutes, for reminders when queue age is under 2 minutes.
7. **Hand off.** Commander posts the timeline, a first list of contributing factors and the owner of the postmortem. SEV1 and SEV2 reviews happen within 5 business days and follow the format of [[postmortem-review-2026-03-24]].

## Escalation

- The commander can call me at any time; I decide on customer-level commitments and external statements with [[renata-castellano]].
- Suspected data exposure: call me immediately; I bring in external privacy counsel ([[abigail-ferris]]) and the SOC 2 incident process.
- Vendor issue (Pingrove, AWS): commander opens the vendor ticket; I call the account contact ([[bettina-solberg]] for Pingrove) if needed.

## Verification

- Every SEV1 and SEV2 has an entry in the [[incident-log]] with timeline, roles and postmortem link.
- The SOC 2 incident response control samples from that log ([[soc2-control-matrix]]).
- We rehearse once a quarter with a 45-minute tabletop exercise; last one 2026-09-22.
