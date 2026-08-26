---
id: ORD-001
type: feature-contract
status: draft
release: build-phase-pending
owner: founder-operations-review
roles: [Customer, MR, Admin, Doctor, Distributor]
workflows: [[workflows/WF-ORD-001 Doctor Attributed Customer Order]]
domain: [[domain/Customer]], [[domain/Customer Order]], [[domain/Doctor]], [[domain/Discount Code]]
screens: [pending]
tests: [pending]
---

# ORD-001 Doctor-Attributed Customer Order

## User outcome

A customer can place a legitimate order while Srasveda retains the correct channel, referring doctor, dedicated MR and optional discount attribution.

## Core rules to retain

- Customer identity/order fulfilment details are separate from clinical/patient information.
- Doctor attribution is optional and must be based on a valid approved source such as doctor-specific link/code or admin/MR selection under policy.
- The order records the MR assignment effective when attribution occurred; later MR reassignment must not rewrite historical attribution.
- Applied discounts are validated and recorded immutably.
- Payment and fulfilment stages are defined by [[requirements/ORD-003 Customer Order Lifecycle and WhatsApp Status]]; no payment state is trusted from a browser-only response.

## Open questions

- [ ] Which customer channels are intended first: public web, WhatsApp, MR-assisted, doctor link, or all?
- [ ] How will a doctor be attributed: referral link, discount code, order selection, or back-office entry?
- [ ] Is a discount a customer benefit, doctor/clinic price rule, campaign benefit, or more than one?
- [ ] What data is required for delivery and who fulfils it?
