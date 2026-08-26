---
type: screen-spec
id: UI-ADM-002
status: draft
roles: [admin, operations]
---

# UI-ADM-002 — Admin Doctor Onboarding and Journey Setup

## Job to be done

An authorised admin can add a doctor to the active network and configure a consistent, personalised MR journey using approved dropdown values—without relying on notes, spreadsheets or a developer to create a new flow.

## Page structure

```text
Doctor onboarding: [Doctor name]                         Save draft | Submit for approval

1. Identity and clinic
   Doctor details | clinic affiliation | zone | professional contact
   Account preparation: approved mobile | [Create pre-provisioned account]

2. Ownership
   Primary MR [dropdown] | manager [dropdown] | relationship tier [dropdown]

3. Product and sampling journey
   Product focus [multi-select: approved active SKUs]
   Sample product [dropdown] | Quantity [dropdown] | [+ Add sample row]
   Feedback checkpoints: 7 days and 1 month after issue
   Feedback outcome set [dropdown]

4. Sales and communication journey
   Sales-checkpoint plan [dropdown]
   Preferred communication language [dropdown]
   WhatsApp permission/status [dropdown/read-only evidence]

5. Review
   Generated journey summary: first task, allowed samples, next checkpoints,
   owner, rules version and any exception

   [Activate onboarding]
```

## Interaction rules

- Every dropdown shows only active, authorised reference options.
- Product focus is a multi-select; only selected products become available for initial visit/sample tasks.
- Each initial sample row uses two controlled dropdowns: product and quantity. Changing product/quantity/checkpoint plan regenerates the **future** task preview before activation.
- An `Add exception` action is restricted to authorised users and requires reason, approver and review/expiry date.
- Activation is disabled until required identity, affiliation, MR, journey and approval fields are valid.
- `Create pre-provisioned account` is available only after the mobile is validated and shows whether that mobile already belongs to an existing customer/account. A conflict opens restricted review; it never creates a duplicate.
- If an existing customer account is selected, `Promote/link to doctor profile` requires the authorised verification step described in [[requirements/AUTH-001 Account Provisioning and Role Activation]].
- After activation, the page becomes a versioned summary. `Change journey` creates a new effective-dated assignment rather than editing history.

## Generated preview example

```text
On activation:
  Day 0: MR task — product introduction for [selected products]
  After recorded sample: feedback tasks due at 7 days and 1 month; each requires an outcome
  After qualifying confirmed order: first-sale review per [selected checkpoint plan]
```

This is a preview of approved business rules, not a medical care plan.

## Must not allow

- Free-text sample quantities, unapproved SKU selection, hidden automation conditions or removal of audit history.
- MR editing of commercial/sampling/checkpoint policy from their field workspace.
- Automatic activation based only on an MR-created doctor record.

## Links

- [[requirements/DOR-001 Doctor Onboarding and Relationship Playbook]]
- [[domain/Doctor Journey Assignment]]
- [[domain/Doctor Relationship Playbook]]
- [[domain/Sales Checkpoint]]
