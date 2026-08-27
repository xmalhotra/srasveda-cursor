---
id: WF-ORD-003
status: draft
---

# WF-ORD-003 — Customer Order Lifecycle

```mermaid
flowchart TD
  A[Checkout creates awaiting-payment order] --> B{Verified payment result?}
  B -- Failed / expired --> C[Append failed/expired event]
  B -- Confirmed --> D[Append payment-confirmed event]
  D --> E[Authorised order confirmation]
  E --> F[Packed]
  F --> G[Dispatched]
  G --> H[Delivered]
  H --> I[After-sales only via ORD-004]
  I --> J[Admin accept/reject]
  J --> K[If payout due: ops pays, then records refunded]

  C --> W[Queue one approved WhatsApp status update]
  D --> W
  E --> W
  F --> W
  G --> W
  H --> W
  K --> W
  W --> K[Record send/delivery result without changing order stage]
```

Each status is an append-only event with source evidence. The WhatsApp update reflects the event; it never creates the event. A customer/doctor request is not an order stage — see [[workflows/WF-ORD-004 Manual After-sales]].
