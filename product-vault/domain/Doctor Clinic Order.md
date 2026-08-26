---
type: domain-object
status: draft
related: [[domain/Doctor]], [[domain/Clinic Hospital]], [[domain/Discount Code]]
---

# Doctor / Clinic Order

An internal-delivery stock-restock supply order made by/for a doctor or clinic. This is distinct from a consumer/customer order.

## Confirmed rules

- It records doctor, clinic context, responsible MR, stock items, agreed commercial terms and internal fulfilment/delivery status.
- The internal delivery team uploads [[domain/Delivery Proof]] at handover; the doctor can view the approved receipt/proof on their order dashboard.
- It does not create a customer order or expose customer data.
- An active [[domain/Order Handling Assignment]] identifies the internal user responsible for operational handling; it does not change the doctor/clinic order ownership.
