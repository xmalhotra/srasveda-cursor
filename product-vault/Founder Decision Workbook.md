---
type: decision-workbook
status: in-progress
owner: founder
---

# Founder Decision Workbook

This is the shortest path from a good blueprint to build-ready specifications. Each proposal is a safe starting point inferred from the current plan—not a decision already made. Mark each `approved`, `change`, or `defer`, record the final wording, then update the linked requirement/ADR.

## A. Customer commerce and fulfilment

| ID | Decision to make | Proposed starting policy | Your decision |
| --- | --- | --- | --- |
| D-01 | Phase-1 order channels | Public/customer direct ordering; doctor/clinic orders are stock-restock supply orders. Official WhatsApp remains structured support/status channel, not an unmanaged order ledger. | Approved 2026-08-09 |
| D-02 | Doctor attribution | Use a unique doctor link or code; direct purchases remain unattributed. Admin corrections require reason and audit. | Pending |
| D-03 | Discount policy | Start only with explicitly approved campaign and doctor-specific customer codes, with dates/limits. Do not allow ad-hoc MR discounts. | Pending |
| D-04 | Fulfilment owner | Internal Srasveda delivery handles launch fulfilment. Delivery staff upload proof/receipt to the order dashboard. | Approved 2026-08-09 |
| D-05 | Customer policies | Publish delivery area/charge, estimated dispatch time, cancellation cut-off, return eligibility and refund method before checkout. **Process locked in ORD-004:** customer/doctor may request in the app or by message; admin decides; refund is manual after payout. Cut-off days and sealed-product rules still pending. | Pending (process locked) |

## B. Doctor onboarding and MR automation

| ID | Decision to make | Proposed starting policy | Your decision |
| --- | --- | --- | --- |
| D-06 | Onboarding approval | Manual admin onboarding/activation. MR may identify candidate but cannot activate doctor. | Approved 2026-08-09 |
| D-07 | Sample control | Admin selects product and quantity from two controlled dropdowns in the journey setup; sample issue remains a recorded human action. | Approved 2026-08-09 |
| D-08 | Feedback checkpoint | Create required feedback tasks at 7 days and 1 month after sample issue; each needs a recorded outcome. Exact outcome list remains to be approved. | Partially approved 2026-08-09 |
| D-09 | Sales checkpoint | First confirmed attributed order creates a first-sale review task; no qualifying repeat in 90 days creates re-engagement task. Exact thresholds remain configurable. | Pending |
| D-10 | Offline use | Launch online-first; decide after an MR connectivity trial whether offline visit capture is needed. | Pending |

## C. Private consultation routing

| ID | Decision to make | Proposed starting policy | Your decision |
| --- | --- | --- | --- |
| D-11 | Customer handoff | Request is shown to operations with mapped location; default mapped partner or authorised manual assignment can be used. Separate consent before sharing customer contact remains required. | Partially approved 2026-08-09 |
| D-12 | Zone matching | Use an internally maintained location/area mapping (for example East Delhi) shown on the consultation dashboard. Exact pincode/city/district rule remains to be defined. | Partially approved 2026-08-09 |
| D-13 | Multiple eligible partners | Use configured default partner for an area; admin/operations can manually assign an eligible partner from dashboard. Priority/rotation beyond this is deferred. | Approved 2026-08-09 |
| D-14 | No match | Show official Srasveda support/contact route; never reveal alternatives or network size. | Pending |
| D-15 | Partner eligibility | Operations approves partner profile, zones, contact card and capacity; admin can suspend immediately. | Pending |

## D. WhatsApp and support

| ID | Decision to make | Proposed starting policy | Your decision |
| --- | --- | --- | --- |
| D-16 | Languages | English and Hindi operational templates at launch, subject to approved final copy. | Pending |
| D-17 | Automatic messages | Pre-structured messages are sent through MSG91. Existing order-status automation remains subject to template approval; marketing remains unapproved. | Partially approved 2026-08-09 |
| D-18 | WhatsApp number/provider | MSG91 with official number `9255427911`; retain/display-name outcome must be confirmed during provider/Meta onboarding. | Partially approved 2026-08-09 |
| D-19 | Support closure | Every Support click creates an internal ticket. Only management/assigned staff receive status notifications and manually close with a reason. | Pending |

## E. Product, content and heritage evidence

| ID | Decision to make | Proposed starting policy | Your decision |
| --- | --- | --- | --- |
| D-20 | SKU launch gate | No product is purchasable until its approved images, price, ingredients/composition, directions, warnings, category and content owner are recorded. | Pending |
| D-21 | Claims review | One named product/regulatory approver signs off each public/professional claim, review and WhatsApp template before publication. | Pending |
| D-22 | Heritage proof | Company-establishment and GST documents exist; Dr Neeru Malhotra founded the business. Upload/verify evidence and approve public wording before publication. | Partially approved 2026-08-09 |
| D-23 | Public endorsements | Use customer reviews, doctor/clinic names, quotes, photographs or logos only with written permission and approved wording. | Pending |

## F. Technical, security and launch

| ID | Decision to make | Proposed starting policy | Your decision |
| --- | --- | --- | --- |
| D-24 | Role access | Separate customer, doctor, MR, fulfilment/distributor, operations/admin and compliance permissions; least privilege by default. | Pending |
| D-25 | Existing-data import | Clean and import doctors, clinics, affiliations, MR assignments, products and prices before launch; do not bulk import unverified historical data. | Pending |
| D-26 | Launch strategy | Pilot with selected MRs, a small verified doctor group and limited customer orders; correct issues before public promotion. | Pending |

## Decision log format

When confirming an item, add an entry:

```text
Decision: D-xx
Outcome: approved / changed / deferred
Final policy:
Owner:
Date:
Linked requirement(s):
```

## Completion rule

When all Phase-1 decisions are confirmed, update the linked requirements from `draft` to `review`, create remaining detailed screen specs and acceptance tests, and then approve a build scope. Do not treat a recommended proposal as a final policy without this confirmation.
