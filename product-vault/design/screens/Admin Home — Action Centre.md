---
type: screen-spec
id: UI-ADM-001
status: draft
roles: [admin, operations]
---

# UI-ADM-001 — Admin Home: Action Centre

## Job to be done

Give the founder/operations team an immediate, trustworthy view of exceptions and decisions requiring intervention, then fast access to the operational areas behind them.

## Page structure

```text
Header: Srasveda Operations | Search | Notifications | Admin profile
Side navigation: Action centre | Network | Commerce | Relationships |
                 Consultation routing | Support | Content & compliance | Security

ACTION CENTRE
  Requires approval: doctor onboarding, MR reassignment, price/policy changes
  Requires action: overdue tasks, feedback/sample exceptions, fulfilment/payment failures
  Attention needed: no-match consultation requests, suspended partners, data-quality issues

TODAY'S OPERATIONS
  Assigned / unassigned work counts, with each count linked to a filtered worklist

RECENT AUDIT ACTIVITY
  Only relevant high-impact changes: price, routing policy, partner eligibility,
  doctor ownership, permission or approved override
```

## Behaviour

- Every item opens an exact record with context, allowed decision options and audit history.
- Counts are action queues, not vanity metrics. They must state the definition/time window.
- High-risk changes (price, partner eligibility, routing policy, permissions) require the approved role and reason.
- Order exceptions show the dedicated doctor/customer, assigned handler, receipt/delivery proof and explicit admin actions to accept/reject cancellation or other permitted correction.
- Consultation routing worklists show status/consent safely; the public never sees these records.
- Support tickets are an internal worklist: assign, add internal notes and manually close with a resolution reason.
- Content & compliance includes the controlled content studio: product photos, decks, copy, banners and approved theme settings.
- Admins may see broad operations data only where their specific permission grants it.

## Must not do

- Expose all partner data in a public/exportable view by default.
- Let an admin silently change historical attribution, price snapshots, completed records or audit history.
- Use a dashboard score as a substitute for reviewing exceptions and source records.

## States to design later

- Founder admin; sales-operations admin; commerce admin; compliance reviewer; no-pending-actions state.

## Links

- [[requirements/UX-001 Role-based Application Experience]]
- [[requirements/CON-001 Consultation Request and Private Partner Routing]]
- [[requirements/DOR-001 Doctor Onboarding and Relationship Playbook]]
