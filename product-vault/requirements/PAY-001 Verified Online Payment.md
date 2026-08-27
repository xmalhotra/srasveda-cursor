---
id: PAY-001
type: feature-contract
status: draft
release: with-ordering
owner: founder-operations-review
roles: [Customer, Admin]
workflows: [[workflows/WF-ORD-003 Customer Order Lifecycle]]
domain: [[domain/Customer Order]], [[domain/Order Status Event]]
screens: [[design/screens/Payment Checkout]]
tests: [pending]
---

# PAY-001 Verified online payment

Srasveda **host adapter** for [[requirements/PAY-CORE Hosted Payment Adapter]]. The module confirms money. This requirement starts packing and WhatsApp only after `payment.confirmed`.

See [[decisions/ADR-002 Reusable Auth and Payment Modules]].

## User outcome

A customer can pay the approved order amount through an authorised hosted checkout. Srasveda marks the order paid only after a verified provider callback or authorised reconciliation.

## Trigger and preconditions

- Trigger: customer taps `Place order and pay` after a valid checkout, or `Pay now` on an awaiting-payment order.
- Preconditions: signed-in customer, server-side price snapshot stored on the order, approved payment provider configured.
- Permission needed: customer may pay only their own order; admin may record a reconciliation event with reason.

## Functional requirements

| ID | Requirement | Priority | Evidence/status |
|---|---|---|---|
| PAY-001-R1 | Checkout creates an `awaiting-payment` order before any provider session. | Must | Draft |
| PAY-001-R2 | Card, UPI and net-banking details are entered only on the approved provider page, never in the Srasveda app. | Must | Draft |
| PAY-001-R3 | `payment-confirmed` is created only from a verified callback/signature or authorised admin reconciliation. A browser return is not enough. | Must | Draft |
| PAY-001-R4 | Failed, cancelled and expired attempts leave the order awaiting payment and do not rewrite the price snapshot. | Must | Draft |
| PAY-001-R5 | A duplicate provider callback for the same payment creates at most one `payment-confirmed` event. | Must | Draft |
| PAY-001-R6 | The customer can pay later from the order. Packing does not start until payment is verified. | Must | Draft |

## Business rules and guardrails

- Amount charged is the immutable order price snapshot, not a client-displayed figure.
- Clinic restock (ORD-002) is not this flow; operations still confirms those payments separately. That exclusion is host policy, not PAY-CORE.
- Refunds are [[requirements/ORD-004 Manual After-sales]]: admin accepts, ops pays outside the app, then records the event. PAY-001 does not auto-reverse the provider.
- Provider brand, keys and settlement account are operational configuration, not UI copy to invent here.
- What must never happen: treat a closed webview as paid; collect PAN/CVV/UPI PIN in Srasveda fields; let a customer mark their own order paid.
- Audit: every attempt, callback, failure and admin reconciliation is an append-only [[domain/Order Status Event]].

## Linked records

- [[requirements/ORD-001 Doctor Attributed Customer Order]]
- [[requirements/ORD-003 Customer Order Lifecycle and WhatsApp Status]]
- [[design/screens/Payment Checkout]]
- [[decisions/ADR-001 Version One Boundary]]
- [[requirements/PAY-CORE Hosted Payment Adapter]]
- [[requirements/ORD-004 Manual After-sales]]
- [[decisions/ADR-002 Reusable Auth and Payment Modules]]
