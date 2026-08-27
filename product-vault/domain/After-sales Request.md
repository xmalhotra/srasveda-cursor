---
type: domain-object
status: draft
---

# After-sales Request

A customer- or doctor-created ask to cancel, return, or otherwise change one order. Operations decides. It is not a payment or a cancellation by itself.

## Fields

- Order, requester account/role, type: `cancel` | `return` | `other`.
- Channel: `in-app` | `whatsapp` | `other-message`.
- Optional customer-safe note.
- Status: `open` → `accepted` | `rejected` → if money is due, `refund-recorded`.
- Linked [[domain/Support Ticket]] for the internal worklist.
- Deciding admin, reason, timestamps. Refund evidence if payout was made.

## Rules

- Open request does not change [[domain/Order Status Event]] history.
- Only authorised admin changes status.
- Refund amount, if any, is the order snapshot (or a recorded partial with reason). The module does not call the payment provider to reverse automatically.
- Duplicate open requests on the same order are rejected.

## Linked records

- [[requirements/ORD-004 Manual After-sales]]
- [[domain/Customer Order]]
- [[domain/Doctor Clinic Order]]
