---
type: domain-object
status: draft
related: [[domain/Visit]], [[domain/Sample]], [[domain/Follow-up]]
---

# Doctor

Represents a healthcare professional/clinic relationship managed by Srasveda. It is not a patient record.

## Minimum attributes

- legal/display name;
- current primary clinic/practice;
- city/area and address as operationally required;
- mobile number;
- speciality/category;
- current dedicated/primary MR assignment;
- lifecycle stage;
- last activity summary;
- next action and due date;
- active/inactive status.

## Relationships

- [[domain/Doctor Clinic Affiliation]] records current and historical association with a clinic/hospital.
- [[domain/Doctor MR Assignment]] records the current dedicated MR and prior assignment history.
- A doctor may be the attributed doctor for a [[domain/Customer Order]] and may also place/request a [[domain/Doctor Clinic Order]].

## Rules

- A doctor can have multiple clinic/hospital affiliations over time; one current primary affiliation may be selected.
- A doctor can have one active primary/dedicated MR at a time unless an approved sharing model is defined.
- A clinic change preserves historical affiliation dates and must not erase visit/order context.
- MR reassignment must be audited with effective dates and reason.
- Doctors can be marked inactive but historical visits/samples remain retained.
