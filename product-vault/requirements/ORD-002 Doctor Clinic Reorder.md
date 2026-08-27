---
id: ORD-002
type: feature-contract
status: draft
release: build-phase-pending
owner: founder-operations-review
roles: [Doctor, MR, Admin, Distributor]
workflows: [[workflows/WF-ORD-002 Doctor Clinic Reorder]]
domain: [[domain/Doctor]], [[domain/Clinic Hospital]], [[domain/Doctor Clinic Order]], [[domain/Doctor MR Assignment]]
screens: [[design/screens/Doctor Order Detail — Receipt and Delivery]], [[design/screens/After-sales Request]]
tests: [pending]
---

# ORD-002 Doctor / Clinic Reorder

## User outcome

A doctor/clinic can request a **stock-restock supply order**. The order is attributed to the correct doctor, current/past clinic context, responsible MR and internal delivery path. Customer direct purchases remain separate [[domain/Customer Order]] records.

## Confirmed rules

- The current primary clinic is suggested, but the order can be explicitly associated with a historical/alternate clinic when valid.
- The dedicated MR receives the order/follow-up visibility defined by policy.
- Doctor, clinic, distributor, MR and customer orders must remain distinguishable in reporting.
- Reorder reminders must not be sent until expected cadence and consent rules are defined.
- A doctor/clinic order is a restock-supply order, not a customer delivery/recommendation-led order.
- Shipping/delivery is handled internally by Srasveda at launch.
- When delivery is completed, the delivery staff uploads a [[domain/Delivery Proof]] (receipt/proof of delivery) to the order dashboard. The doctor sees the customer-safe receipt/proof; operations sees the full delivery audit.

## Dashboard permissions

| Role | May view | May change |
| --- | --- | --- |
| Dedicated doctor / clinic account | Only its own order summary, order receipt, delivery receipt/proof and customer-safe status timeline | May submit an in-app or message after-sales request; cannot directly alter order data |
| Assigned order handler | Only assigned order(s), fulfilment/delivery fields and required delivery proof | Record packing/delivery checkpoints and upload proof; cannot change price, discount, order ownership or historical attribution |
| Admin / authorised operations | All required order, receipt, assignment and audit records | Assign handler, approve/reject cancellation, correct authorised exceptions and manage fulfilment status with reason/audit |
| MR | Only policy-permitted attributed order signal | No direct fulfilment, price or cancellation authority by default |

### Admin authority guardrails

- Cancellation, price/discount correction, order reassignment, refund/return decision and any exception requires an authorised admin action, reason and audit entry.
- Admin correction adds an authorised event; it must not silently rewrite the original receipt, delivery proof, price snapshot or historical status.
- A cancellation/return request is not a cancellation until admin accepts it. Refund is recorded after ops has paid it. Same contract as [[requirements/ORD-004 Manual After-sales]].

## Open questions

- [ ] What doctor/clinic price/discount agreement applies to restock supply, and who may approve it?
- [ ] What exact delivery fields, delivery-area rule, cancellation/return rule and tax invoice requirements apply?
