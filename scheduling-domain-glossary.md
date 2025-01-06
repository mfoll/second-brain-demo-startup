---
type: Note
belongs_to: "[[deliver-the-product]]"
related_to:
  - "[[appointment-scheduling]]"
  - "[[appointment-slot-model]]"
_organized: true
---

# Scheduling Domain Glossary

The words clinic staff use, what they mean in Quaylane, and where they live in the schema. Written for new engineers; Ayesha and Bram both used it in their first week.

| Term | Meaning | Table or field |
| --- | --- | --- |
| Book | All appointments of a site for a day or week | view over `appointments` |
| Site | One physical clinic location | `sites` |
| Organization | A customer account, possibly with many sites | `organizations` (the tenant) |
| Practitioner | Staff member who sees patients | `staff` with `bookable = true` |
| Roster | When a staff member works, by site | `roster_entries` |
| Room | A bookable space, or equipment modeled as one | `rooms` |
| Appointment type | Clinic-defined label with a default length | `appointment_types` |
| Hold | A temporary claim on a time range | `holds` |
| Waitlist entry | A person waiting for an earlier slot, with availability | `waitlist_entries` |
| DNA | "Did not attend", the front-desk term for a no-show | `appointments.status = 'no_show'` |
| Recall | A reminder that a periodic visit is due; not built | none yet |

## Words to avoid

- "Patient record": we do not keep records in the clinical sense. We keep a name, contact details and appointments. Say "contact".
- "Tenant" in customer conversations. Customers say "account".

See also [[no-show-rate]] and [[scheduling-engine-overview]].
