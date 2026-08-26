---
type: relationship-object
status: draft
from: [[domain/Doctor]]
to: MR
---

# Doctor–MR Assignment

Records which MR is dedicated to a doctor for follow-ups and relationship ownership.

| Field | Required | Rule |
|---|---:|---|
| doctor | Yes | Existing active doctor |
| MR | Yes | Existing active MR |
| effective from | Yes | Start date/time |
| effective to | No | Filled when reassigned/ended |
| primary | Yes | One active primary MR per doctor unless approved exception |
| assignment reason | Yes | Initial assignment, territory change, handover or correction |

## Guardrails

- Only Admin may create/end/reassign a primary assignment.
- An MR can access a doctor only while the assignment is active, except a narrowly defined handover/audit view.
- Reassignment must preserve prior visit, sample and order attribution.
