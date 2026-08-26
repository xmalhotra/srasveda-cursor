---
type: domain-object
status: discovery
related: [[domain/Customer Order]], [[domain/Doctor]], [[domain/Customer]]
---

# Discount Code

A controlled commercial rule applied to an eligible order. It is not merely a text field on checkout.

## Required future fields

- code and active status;
- benefit type: percentage, fixed amount, bundle/other approved type;
- eligibility: public, customer segment, specific doctor, clinic, MR campaign or order type;
- start/end date and usage limits;
- minimum order/product exclusions;
- attribution target where applicable;
- redemption history, order link and applied value;
- approval owner and reason.

## Guardrails

- Expired/inactive codes cannot be applied.
- A completed order keeps an immutable record of the code and discount used.
- The system validates eligibility server-side; the browser cannot choose a larger discount.
- Discount policy and any doctor benefit/attribution must be reviewed for commercial and regulatory appropriateness before launch.
