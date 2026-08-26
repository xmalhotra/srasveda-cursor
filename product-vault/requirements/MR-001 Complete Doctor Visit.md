---
id: MR-001
type: feature-contract
status: draft
release: phase-1
owner: founder-and-mr-review
roles: [MR, Admin]
workflows: [[workflows/WF-MR-001 Clinic Visit]]
domain: [[domain/Doctor]], [[domain/Visit]], [[domain/Sample]], [[domain/Follow-up]]
screens: [UI-MR-05-pending]
tests: [[tests/MR-001 Complete Doctor Visit Test]]
decisions: [[decisions/ADR-001 Version One Boundary]]
---

# MR-001 Complete Doctor Visit

## User outcome

An assigned MR can finish a doctor interaction with a reliable, quick record of what happened and what must happen next. The next MR action cannot be lost in a notebook, memory or WhatsApp chat.

## Trigger and preconditions

- Trigger: MR selects **Log visit** from a doctor profile.
- Preconditions: MR is authenticated, active, and assigned to the selected doctor.
- Permission: only the assigned MR may create or edit their own visit record; Admin may review it.

## Functional requirements

| ID | Requirement | Priority | Evidence/status |
|---|---|---|---|
| MR-001-R1 | Show the doctor identity, clinic, current lifecycle stage and latest recorded next action before entry. | Must | Draft |
| MR-001-R2 | Record visit date/time, products discussed, doctor response and an optional concise note. | Must | Draft |
| MR-001-R3 | Allow one or more samples to be recorded against the visit. | Must | Draft |
| MR-001-R4 | Require a next-action type and due date before a visit can be completed. | Must | ASSUMPTION — needs MR confirmation |
| MR-001-R5 | Create/refresh a linked follow-up task when the visit is completed. | Must | Draft |
| MR-001-R6 | Preserve a chronological history of completed visits. | Must | Draft |
| MR-001-R7 | Allow the MR to share approved product resources after the visit without exposing internal information. | Should | Draft |

## Business rules and guardrails

- The selected doctor must belong to the signed-in MR; server/database enforcement is required.
- A visit must never be written for an inactive or deleted doctor.
- A sample record must reference a valid active product and a positive quantity.
- Completing a visit without a next action/due date is blocked unless an explicitly approved exception is defined.
- Visit records are not silently deleted. Correction requires an audit event containing actor, timestamp and reason.
- Internal notes, MR-only product guidance and other doctor records must never appear in doctor-facing shared links.

## Data contract

| Field | Required | Source | Validation | Visibility |
|---|---:|---|---|---|
| doctor_id | Yes | Doctor profile context | Must be assigned to MR | MR/Admin |
| mr_id | Yes | Authenticated session | Must equal assigned MR | MR/Admin |
| occurred_at | Yes | Default current time; editable | Cannot be future unless approved | MR/Admin |
| products_discussed | Yes | Product selector | At least one active product | MR/Admin |
| doctor_response | Yes | Controlled option set | Values pending discovery | MR/Admin |
| note | No | MR input | Length limit pending | MR/Admin |
| next_action_type | Yes | Controlled option set | Values pending discovery | MR/Admin |
| next_action_due_at | Yes | Date selector | Date rule pending | MR/Admin |
| sample_items | No | Sample sub-form | Each quantity is positive | MR/Admin |

## Side effects

On successful completion:

1. Create an immutable visit timeline entry.
2. Create or update a [[domain/Follow-up]] owned by the assigned MR.
3. Update the doctor’s `last_activity_at` and `next_action` summary.
4. If samples exist, create linked [[domain/Sample]] records and feedback due dates.
5. Write an audit event.

## UX contract

- Screen: `UI-MR-05 Log Visit` — not yet designed.
- Required states: default, no assigned doctor/access denied, validation errors, saving, saved, server error, offline behaviour decision pending.
- Phone: single-column, quick-entry form.
- Tablet: same form; no extra desktop-only fields.
- Target: the MR can complete a routine post-visit record in two minutes or less.

## Out of scope

- Patient health records or patient identifiers.
- Invoice creation, payment collection or distributor fulfilment.
- Automated clinical recommendations.
- Public display of MR notes.

## Open questions

- [ ] What exact doctor-response choices do MRs use today?
- [ ] Can one visit have products discussed but no samples? Expected: yes; validate.
- [ ] Can an MR change a completed visit? If yes, within what period and with which approval?
- [ ] Is offline entry required in Haryana clinic locations for Phase 1?
- [ ] What is the accepted due-date rule for a sample feedback follow-up?

## Change history

| Date | Change | Why | Author/approver |
|---|---|---|---|
| 2026-08-08 | Initial feature contract created | Begin specification process | Codex / pending founder-MR review |
