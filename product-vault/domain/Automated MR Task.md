---
type: domain-object
status: draft
---

# Automated MR Task

A tracked action created by an approved [[domain/Doctor Relationship Playbook]] rule for the doctor’s assigned MR.

## Fields

- Doctor, assigned MR, optional product and source playbook/checkpoint version.
- Task type, due date, priority and clear completion evidence.
- Status: `open`, `in-progress`, `completed`, `overdue`, `waived`, `cancelled`.
- Completion note/evidence; waiver/override reason; escalation record.

## Rules

- Tasks are visible to the assigned MR and authorised manager/admin only.
- An overdue task triggers the approved reminder/escalation path but never sends an unapproved customer/doctor message automatically.
- A reassignment changes future ownership while retaining the original task/audit history.
