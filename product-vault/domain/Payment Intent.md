---
type: domain-object
status: draft
module: reusable
---

# Payment Intent

A payable registered by [[requirements/PAY-CORE Hosted Payment Adapter]] before a provider session starts. The host’s order (or invoice) stays a separate record.

## Required fields

- Host payable id (opaque to the module), payer account, amount, currency, snapshot id.
- Status: `created` → `session-open` → `pending` → `confirmed` | `failed` | `cancelled` | `expired`.
- Provider, provider session/attempt id, idempotency key.
- Evidence: verified callback payload reference or admin reconciliation note.

## Rules

- Amount is the host snapshot. The module does not re-price.
- Attempts are append-only. A new pay session is a new attempt, not an edit of a failed one.
- `confirmed` requires verified provider evidence or authorised reconcile.
- Duplicate provider events with the same idempotency key do not create a second confirmation.

## Host adapter

Srasveda’s payable is a [[domain/Customer Order]] in `awaiting-payment`. Fulfilment stages live on [[domain/Order Status Event]], not on this object.
