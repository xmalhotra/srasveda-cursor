---
id: PRD-003
type: feature-contract
status: draft
release: phase-1
roles: [MR, Admin]
domain: [[domain/Doctor Product Relationship]], [[domain/Product]], [[domain/Sample]]
---

# PRD-003 Next Sample Queue

## User outcome

The MR can see a transparent, reviewable queue of potential next product samples for an assigned doctor, based on known product relationship gaps and approved business rules.

## Initial rule model

Show candidates only when a product is active, sample-eligible, not already in an unresolved feedback state for that doctor, and matches an explicitly configured non-clinical interest/segment rule. Show *why* it appears, for example: “Doctor has discussed Product A; no sample recorded for Product B in this approved women’s wellness segment.”

## Guardrails

- This is an MR decision aid, not automatic clinical advice or prescription generation.
- The MR can dismiss a suggestion with a reason; it is never automatically issued.
- Every rule and reason is visible to Admin and auditable.
- No patient-level information is used.

## Open questions

- [ ] Which product segments/interests are valid for internal business tagging?
- [ ] What blocks a product from being sampled again and for how long?
- [ ] Should admin configure rules manually before any automated ranking is allowed?
