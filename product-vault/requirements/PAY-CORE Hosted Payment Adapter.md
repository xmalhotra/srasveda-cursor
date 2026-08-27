---
id: PAY-CORE
type: feature-contract
status: draft
release: with-ordering
owner: platform
roles: [payer, ops-reconcile]
module: reusable
workflows: []
domain: [[domain/Payment Intent]]
screens: [[design/screens/Payment Checkout]]
tests: [pending]
decisions: [[decisions/ADR-002 Reusable Auth and Payment Modules]]
---

# PAY-CORE — Hosted payment adapter

Reusable payment module. It starts a payable, opens an approved provider, and records a verified result. It does not pack, ship, or send WhatsApp.

## User outcome

A signed-in payer can pay a host-supplied amount on a hosted checkout. The host is told paid / failed / cancelled / expired / pending only after a verified provider result or authorised reconciliation.

## Plug-and-play surface

| Host supplies | Module owns |
|---|---|
| Payable reference, amount, currency, snapshot id | Payment intent and attempt records |
| Signed-in payer id | Hosted redirect / provider session |
| Method list (e.g. UPI, card, net banking) | No PAN / CVV / UPI PIN fields in the host app |
| Provider adapter (verify signature, idempotency key) | Confirming UI until verified result |
| `onPaymentResult(intent, result)` | Duplicate callbacks → one confirmed result |
| Ops reconcile permission | Admin “not verified” record-with-evidence |

Swap the host: new order object, new provider keys, new method list, new post-pay screen. Do not put card fields in the product app. Do not treat a closed webview as paid.

## Functional requirements

| ID | Requirement | Priority |
|---|---|---|
| PAY-CORE-R1 | A payment intent exists before the provider session. Amount is the host snapshot, not a client price. | Must |
| PAY-CORE-R2 | Secrets stay on the provider page. | Must |
| PAY-CORE-R3 | `confirmed` only from verified callback/signature or authorised reconcile. | Must |
| PAY-CORE-R4 | Failed, cancelled and expired leave the intent unpaid. Snapshot is not rewritten. | Must |
| PAY-CORE-R5 | The same provider event confirms at most once. | Must |
| PAY-CORE-R6 | Pay-later is allowed. The host decides whether fulfilment may start. | Must |

## Events the host must handle

| Event | When | Host does |
|---|---|---|
| `payment.intent_created` | Payable registered | Keep business record in `awaiting-payment` (or host equivalent) |
| `payment.confirmed` | Verified provider result | Advance host workflow (e.g. allow packing) |
| `payment.failed` / `cancelled` / `expired` | Terminal unsuccessful attempt | Keep unpaid; allow retry if host policy says so |
| `payment.pending` | Return from provider, no callback yet | Show confirming; do not start a second session unless failed/expired |

## Out of scope (host adapter)

Customer order packing, WhatsApp, clinic restock, doctor attribution, automatic provider refunds. Those are [[requirements/PAY-001 Verified Online Payment]], ORD-003, and [[requirements/ORD-004 Manual After-sales]]. A host may later automate reverse; this module does not require it. Srasveda records refunds manually after payout.

## UX contract

Screens on Figma page `07 Payment — Checkout`. Chrome is [[requirements/DS-CORE Shared UI System]]. Provider brand is configuration, not a frame. The provider page itself is not designed in this file.

## Acceptance scenarios

- Given a payable snapshot, when the provider callback verifies, then the host receives `payment.confirmed` once even if the webhook repeats.
- Given the payer closes the provider page, when they return, then status is cancelled or pending — never confirmed.
- Given no callback, when ops reconciles with evidence, then `payment.confirmed` or `failed` is appended, not a silent edit of history.
