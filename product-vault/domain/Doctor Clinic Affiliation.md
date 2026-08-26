---
type: relationship-object
status: draft
from: [[domain/Doctor]]
to: [[domain/Clinic Hospital]]
---

# Doctor–Clinic Affiliation

Records where a doctor practises over time.

| Field | Required | Rule |
|---|---:|---|
| doctor | Yes | Existing doctor |
| clinic/hospital | Yes | Existing or newly created clinic |
| started on | Yes | Date known or estimated flag |
| ended on | No | Required when affiliation is no longer current |
| primary | Yes | At most one active primary affiliation per doctor |
| role/title | No | Optional practice role |
| change reason | No | Required by policy if correcting history |

Visits and orders should retain a snapshot/reference to the relevant clinic context where necessary.
