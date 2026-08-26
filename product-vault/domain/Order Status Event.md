---
type: domain-object
status: draft
---

# Order Status Event

An immutable record of a real payment, fulfilment or after-sales checkpoint for one [[domain/Customer Order]]. It supports operations, customer order history and a single linked WhatsApp status update.

## Customer-facing order stages

```text
awaiting-payment → payment-confirmed → order-confirmed → packed → dispatched → delivered
```

Alternative/end states:

```text
payment-failed | payment-expired | cancelled | return-requested → return-received → refund-pending → refunded
```

## Required event fields

- Order, old stage, new stage, occurred-at time and actor/source.
- Evidence/reference: payment gateway event, fulfilment action, courier tracking event or authorised admin action.
- Customer-visible label and approved next action, where applicable.
- Reason for cancellation, return or exception, using customer-safe wording.
- Linked [[domain/Communication Event]] status where notification is attempted.

## Rules

- Events are append-only. Corrections add a new authorised event; history is never silently rewritten.
- Valid transitions are enforced. For example, an order cannot become `dispatched` before it is confirmed/accepted for fulfilment.
- Payment confirmation is created only from a verified server-side gateway callback or approved reconciliation—not browser success UI.
- Each eligible event has an idempotency key, so a retry/provider webhook cannot create duplicate stages or WhatsApp notifications.
- Customer status uses plain language; internal logistics detail stays internal.
