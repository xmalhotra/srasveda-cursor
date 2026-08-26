---
type: domain-object
status: draft
---

# Order Handling Assignment

The active, auditable assignment of an order to an authorised internal user responsible for its operational handling.

## Fields

- Order, assigned handler, assignment date, assigned by and status.
- Scope: fulfilment preparation, delivery handover, proof upload, exception escalation.
- Reassignment reason, effective time and audit history.

## Rules

- An assigned handler sees only orders assigned to them, unless a higher authorised role grants temporary coverage.
- Handling assignment does not grant authority to edit price, discount, attributed doctor, order ownership, historical events or financial records.
- A handler may record only authorised operational checkpoints and upload [[domain/Delivery Proof]].
- Admin can assign/reassign/withdraw the assignment with an audit reason.
