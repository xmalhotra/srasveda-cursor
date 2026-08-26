---
type: domain-object
status: draft
---

# Doctor Relationship Playbook

The approved, versioned checklist that guides an MR from bringing a doctor into the network through product education, sampling, feedback and sales-based follow-up.

## Stages

1. `candidate` — doctor identified; not yet accepted into the active network.
2. `qualification` — profile, clinic affiliation, territory and dedicated MR verified.
3. `onboarded` — required approval complete; relationship is active.
4. `introduced` — selected product/resource presented.
5. `sample-follow-up` — sample issued and feedback checkpoint due.
6. `activated` — first qualifying attributed sale or clinic order recorded.
7. `growing` — recurring activity meets approved checkpoint rules.
8. `at-risk` — required feedback, follow-up or sales checkpoint is overdue.
9. `paused` or `closed` — relationship intentionally stopped, with reason.

## Checklist templates

A playbook is a reusable template, not hard-coded application logic. Each item has:

- stage, owner role and due-date rule;
- required evidence/input and completion condition;
- optional product, doctor tier or territory applicability;
- task/reminder/escalation behaviour;
- approval status and effective version.

## Core rules

- Every doctor is assigned one active playbook version and a primary MR before automated tasks start.
- Automation creates tasks; it does not fabricate an MR visit, feedback, sample, sale or doctor consent.
- Completing a checklist item requires the recorded evidence specified by that item.
- Playbook changes apply prospectively. Existing tasks retain the version that created them.
- All manual overrides, skipped items and reassignment decisions require reason and audit history.
