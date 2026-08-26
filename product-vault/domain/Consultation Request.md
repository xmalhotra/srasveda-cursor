---
type: domain-object
status: draft
---

# Consultation Request

A request to connect a customer to one approved Srasveda partner near them. It is not a diagnosis, prescription, clinical record or medical recommendation.

## Minimum data

- Customer/guest contact details; city and/or pincode; optional language/contact-time preference.
- Status: `new`, `routing`, `contact-shown`, `lead-shared`, `contacted`, `closed`, `cancelled`.
- Privacy-notice version and explicit consent record.
- Linked [[domain/Referral]], if routed.

## Deliberate exclusions

- Symptoms, diagnosis, prescriptions, test reports or other patient/medical-record data.
- A public list, map or searchable index of all clinics/doctors in the network.

## Rules

- A direct [[domain/Customer Order]] does not require consultation.
- Showing a selected clinic's contact and sharing a customer's details with that clinic are distinct actions.
- Consent, routing decision and every status change are auditable.
