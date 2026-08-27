---
id: ORD-004
type: feature-contract
status: draft
release: with-ordering
owner: founder-operations
roles: [Customer, Doctor, Admin]
workflows: [[workflows/WF-ORD-004 Manual After-sales]]
domain: [[domain/After-sales Request]], [[domain/Support Ticket]], [[domain/Order Status Event]]
screens: [[design/screens/After-sales Request]]
tests: [pending]
---

# ORD-004 — Manual after-sales (cancel, return, refund)

## User outcome

A customer or doctor can ask to cancel, return or otherwise change an order **in the app** (or by message). Operations sees it on the admin action centre and decides. Money is refunded only after a human accepts and records the payout. Nothing auto-cancels or auto-refunds.

Low order volume is the reason: review is cheaper and safer than an automated refund pipeline.

## Trigger and preconditions

- Trigger: in-app `Request` on an order, or a WhatsApp/message that operations files against that order.
- Preconditions: signed-in requester, own order only.
- Permission: requester may create a request; only authorised admin may accept, reject, or record a refund.

## Functional requirements

| ID | Requirement | Priority | Evidence/status |
|---|---|---|---|
| ORD-004-R1 | In-app request types: `cancel`, `return`, `other`. Optional short note. No medical details. | Must | Draft |
| ORD-004-R2 | The same record is created if the ask arrived by WhatsApp/message and staff link it to the order. | Must | Draft |
| ORD-004-R3 | Creating a request does not change order stage, payment, or stock. | Must | Draft |
| ORD-004-R4 | Action centre shows a new item for authorised admin. The requester does not get a ticket portal. | Must | Draft |
| ORD-004-R5 | Admin accept/reject requires a reason and audit. Accept may then require a **manual refund** step. | Must | Draft |
| ORD-004-R6 | Refund is recorded after operations has paid it (bank/UPI/provider dashboard). No automatic gateway refund. | Must | Draft |
| ORD-004-R7 | One open request per order unless admin closes it. A second in-app submit is blocked with “already in review”. | Must | Draft |

## Business rules

- Cancel vs return is a hint for ops, not a right. Admin may refuse under unpublished or published policy.
- Cut-off days and sealed-product rules remain [[Founder Decision Workbook]] D-05; this requirement only locks **who decides** and **that refund is manual**.
- Doctor restock uses the same request + admin control; it is not a customer self-serve return portal.
- WhatsApp after an authorised event (cancelled, refund recorded) follows ORD-003. That is an order-status message, not a support-ticket notification.
- What must never happen: customer/doctor marks paid, cancelled, or refunded; a message or elapsed time closes the request; a provider webhook issues a refund without admin accept.

## Acceptance scenarios

- Given an order, when the customer submits cancel in the app, then admin sees it in the action centre and the order stage is unchanged.
- Given a WhatsApp cancel ask, when ops links it to the order, then it is the same queue item as an in-app request.
- Given admin rejects, when they save a reason, then the request closes and the order is not cancelled.
- Given admin accepts a paid cancel, when they later record refund with evidence, then `refunded` is appended — the accept click alone does not move money.
