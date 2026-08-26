---
id: COM-001
type: feature-contract
status: draft
release: phase-1-foundation
owner: founder-operations-content-review
roles: [Admin, MR, Doctor, Customer, Distributor]
workflows: [[workflows/WF-COM-001 WhatsApp Updates]]
domain: [[domain/Communication Preference]], [[domain/Communication Event]], [[domain/Doctor]], [[domain/Customer Order]], [[domain/Follow-up]]
screens: [pending]
tests: [pending]
---

# COM-001 WhatsApp Updates

## User outcome

Doctors, customers, distributors and MRs receive useful, timely, approved WhatsApp updates linked to real Srasveda activity—without relying on untracked personal chats or sending unwanted messages.

## Update classes

| Recipient | Triggered update | Purpose | Phase |
|---|---|---|---|
| Doctor | Product/resource link after a visit | Professional resource follow-up | Phase 1 |
| Doctor | Sample-feedback reminder / MR contact | Relationship follow-up | Phase 1 after consent/rules |
| Customer | Order received, payment result, packed, dispatch, delivery, cancellation/refund update | Operational | With ordering |
| Customer | Reorder reminder/product update | Optional relationship/marketing | Later, consent required |
| Distributor | New allocated order / status action | Operational | With fulfilment |
| MR | Daily due-follow-up digest / reassignment update | Internal operational | Phase 1 if useful |

## Functional requirements

| ID | Requirement | Priority | Evidence/status |
|---|---|---|---|
| COM-001-R1 | Send only approved templates with controlled variables; free-form system messages are not allowed. | Must | Draft |
| COM-001-R2 | Check communication preference/eligibility before optional messages are queued. | Must | Draft |
| COM-001-R3 | Link every message attempt to its source record and recipient. | Must | Draft |
| COM-001-R4 | Record provider status and failures without changing the source business record. | Must | Draft |
| COM-001-R5 | Let an MR initiate an approved doctor resource message from a visit/doctor context. | Must | Draft |
| COM-001-R6 | Support event-driven order/payment/fulfilment notifications when those modules are approved. | Must | Draft |
| COM-001-R7 | Apply frequency limits to optional reminders and marketing. | Must | Draft |
| COM-001-R8 | For a qualifying customer-order status transition, send at most one approved operational status update and link it to the immutable order event. | Must | Draft |

## Business rules and guardrails

- Message content is selected from an approved template library and is versioned.
- The system must not send optional updates to an opted-out recipient.
- The system must never expose patient data, internal notes, internal pricing/margins, other doctors, or unapproved health/product claims.
- A send failure creates a communication failure event; it does not silently mark an order/payment/follow-up as complete.
- The user interface must distinguish `sent`, `delivered/read if available`, `failed`, and `business action complete`.
- Regular messages need cadence rules; a doctor/customer must not receive repeated reminders simply because a job retries.
- Order status messages are operational updates, distinct from optional marketing. A retry must not result in duplicate customer messages for the same status event.
- The message must say the customer-facing order status and approved next action/support route; it must never expose internal fulfilment notes, staff identity, margin or unrelated data.

## Technical integration boundary

- **Confirmed provider direction:** use MSG91 for pre-structured WhatsApp templates from the official Srasveda number **9255427911**, subject to MSG91/Meta onboarding and approval.
- The existing number should be retained if the provider onboarding supports it. The final WhatsApp Business display name/contact presentation must be confirmed during onboarding; do not assume MSG91 will change it or preserve it without written/provider confirmation.
- The provider receives only the minimum recipient/template parameters needed for the message.
- Provider callbacks/webhooks update [[domain/Communication Event]] after signature verification.
- Sending happens server-side; API keys are never exposed in the browser.

## Out of scope

- Replacing all personal MR–doctor conversations with automation.
- Unrestricted marketing broadcasts.
- AI-generated clinical/medical messages.
- Treating WhatsApp read receipts as proof that a doctor approved, ordered or received a product.

## Open questions

- [ ] Which updates should be automatic versus initiated by an MR/admin?
- [ ] What languages are required first: English, Hindi, both, or others?
- [ ] What frequency is acceptable for sample reminders and reorder messages?
- [ ] Who approves every product/resource template before use?
- [ ] Confirm MSG91/Meta onboarding outcome for number `9255427911`, final display name, template approval and coexistence/migration approach.
