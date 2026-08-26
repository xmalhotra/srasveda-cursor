---
type: domain-object
status: draft
related: [[domain/Customer]], [[domain/Doctor]], [[domain/Discount Code]]
---

# Customer Order

An order placed by a customer, potentially attributed to a doctor, MR, campaign or direct public channel.

## Required attribution design

An order source and an optional attributed doctor are separate concepts:

- `source`: customer self-order, MR-assisted, doctor-assisted, admin-assisted, distributor-assisted;
- `attributed_doctor`: the doctor whose recommendation/referral is associated with the order, when applicable;
- `attributed_mr`: the MR responsible for the doctor relationship at the time of order;
- `discount_code`: optional applied code, with immutable redemption record.

## Pricing rules

- Srasveda controls customer prices through approved [[domain/Product Price]] records.
- The server calculates the selling price, tax, discount and final total at checkout; the browser cannot submit its own price.
- Every confirmed order retains an immutable price, tax, discount and total snapshot, even when the catalogue price changes later.
- An order may optionally link to a [[domain/Consultation Request]]; consultation is never required to buy.

## Lifecycle tracking

- The current customer-visible stage and the complete immutable [[domain/Order Status Event]] timeline are separate; the timeline explains how the order reached its present state.
- Only authorised payment/fulfilment events may advance an order stage. A status cannot be changed merely because a WhatsApp message was sent or read.
- Each qualifying stage transition can create one tracked [[domain/Communication Event]] using an approved operational WhatsApp template.

This preserves correct reporting if a customer orders online but is connected to a doctor.
