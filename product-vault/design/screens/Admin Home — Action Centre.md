---
type: screen-spec
id: UI-ADM-001
status: draft
roles: [admin, operations]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2815
---

# UI-ADM-001 — Admin Home: Action Centre

## Job to be done

Give the founder/operations team an immediate, trustworthy view of exceptions and decisions requiring intervention, then fast access to the operational areas behind them.

## Page structure

```text
Header: Srasveda | Profile avatar
Bottom navigation: Home | Network | Commerce | More
More opens Support, Content studio, Consultation routing and Security.
Focused records use back + sticky action, same as MR visit.

ACTION CENTRE
  Requires approval: doctor onboarding, MR reassignment, price/policy changes
  Requires action: overdue tasks, after-sales requests (in-app or message), fulfilment/payment failures
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
- Order exceptions show the dedicated doctor/customer, assigned handler, receipt/delivery proof, request channel (in-app or WhatsApp/message) and explicit admin actions to accept/reject. Accept does not pay a refund. If money is due, ops pays it then records the refund with evidence.
- Consultation routing worklists show status/consent safely; the public never sees these records.
- Support tickets are an internal worklist: assign, add internal notes and manually close with a resolution reason.
- Content & compliance includes the controlled content studio: product photos, decks, copy, banners and approved theme settings.
- Admins may see broad operations data only where their specific permission grants it.

## Must not do

- Expose all partner data in a public/exportable view by default.
- Let an admin silently change historical attribution, price snapshots, completed records or audit history.
- Use a dashboard score as a substitute for reviewing exceptions and source records.

## Designed states

| State | Frame |
| --- | --- |
| Action centre | [Action centre](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2815) |
| No open exceptions | [Action centre — clear](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2898) |
| Loading | [Action centre — loading](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2949) |
| Commerce | [Commerce](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3227) |
| Cancellation review | [Cancellation review](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3310) |
| After-sales | [[design/screens/After-sales Request]] |
| Consultation routing | [Consultation routing](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3497) |
| More | [More](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3543) |
| Access denied | [Access denied](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3626) |

## Links

- [[requirements/UX-001 Role-based Application Experience]]
- [[requirements/CON-001 Consultation Request and Private Partner Routing]]
- [[requirements/DOR-001 Doctor Onboarding and Relationship Playbook]]
- [[requirements/ORD-004 Manual After-sales]]
