---
type: screen-spec
id: UI-DOC-002
status: draft
roles: [doctor]
---

# UI-DOC-002 — Doctor Order Detail: Receipt and Delivery

## Purpose

Let a doctor view their own restock order and its receipts/proof without exposing internal operations or allowing uncontrolled changes.

```text
Order #[reference]                         Current status: Delivered
Clinic / delivery location (approved view)

Items and approved order total
Order receipt                               [View / Download]
Delivery timeline: confirmed → packed → delivered
Delivery receipt / proof                    [View]

Need help with this order?                  [Support]
Request cancellation (when policy allows)   [Request]
```

## Boundaries

- The doctor sees only their own order and customer-safe receipt/proof.
- There are no edit-price, edit-item, edit-status, edit-handler or direct-cancel controls.
- `Request cancellation` creates a support/order-exception item for authorised admin review; it does not cancel immediately.
