---
type: domain-object
status: draft
---

# Doctor Journey Assignment

The auditable, per-doctor configuration selected by admin at onboarding. It personalises a [[domain/Doctor Relationship Playbook]] without creating hidden, one-off automation logic.

## Selected configuration

- Doctor tier / relationship type.
- Published playbook version.
- Product focus set: active approved SKUs only.
- Sampling plan version: eligible SKUs, quantity/max, repeat cooldown and approval rule.
- Initial sampling rows: one or more `(active product, allowed quantity)` selections made from controlled dropdowns.
- Follow-up cadence: fixed 7-day and 1-month feedback checkpoints after every recorded sample; approved feedback-outcome options.
- Sales-checkpoint plan version.
- Communication preference/language and primary MR/manager owner.

## Lifecycle

`draft → submitted-for-approval → active → superseded → paused`

## Rules

- Only one `active` assignment may govern a doctor at a time.
- Assignment creation is part of onboarding approval; no automated MR task starts before it becomes active.
- A change creates a new version/effective date and audit record. It does not rewrite prior tasks, samples, feedback or sales checkpoints.
- A per-doctor exception must carry reason, approver and expiry/review date.
- The assignment contains business relationship settings only, never medical diagnosis, treatment plan or patient information.
