---
id: CON-001
title: Consultation request and private partner routing
status: draft
owner: business-owner
priority: must-have-before-public-consultation
---

# CON-001 — Consultation Request and Private Partner Routing

## User outcome

A customer buys directly at the Srasveda-set price. If they request consultation, the platform connects them with one suitable approved partner contact near them without revealing the Srasveda clinic/doctor network.

## Scope

- Optional “Need a consultation?” action from public product/order journeys.
- Minimal contact and zone collection; no medical intake or diagnosis.
- Privacy notice and explicit consent before a customer's details are shared with a partner.
- Server-side selection of one partner using [[domain/Referral Routing Policy]].
- Admin dashboard worklist showing each request, mapped location/zone, default partner (where configured) and manual assignment option.
- One approved clinic/doctor card with address and call/WhatsApp action.
- Admin-only partner registry, availability, caps, priorities, policy versions and audit trail.
- Neutral no-match/escalation path.

## Non-goals

- A public doctor/clinic directory, map, searchable hospital database or network export.
- Medical advice, diagnosis, appointment booking, prescription handling or patient records.
- A claim that an internally prioritised partner is clinically “best”.

## Direct-order pricing rules

- [[domain/Product Price]] is the source of approved selling price.
- Checkout calculates amounts server-side and stores an immutable snapshot on [[domain/Customer Order]].
- A consultation request never alters price unless an approved discount rule applies.

## Referral-routing rules

- The eligible pool remains private; the customer sees only one selected contact card.
- With several partners in one zone, the policy applies eligibility, capacity/cooldown and approved priority, then auditable fair rotation where required.
- A suspended, unavailable or capped partner is never selected.
- **Confirmed policy:** resolve the request location (for example East Delhi) to an internal mapped zone. If an active default partner is configured for that zone, it may be selected; authorised operations/admin may instead manually assign an eligible partner after reviewing the dashboard request and mapped location. The selected partner remains the only partner exposed to the customer.
- A manual assignment records who selected it and why; it never reveals alternate eligible clinics to the customer.
- Showing a contact card and sharing a customer lead are separate; lead sharing requires recorded consent.
- Routing decisions and later changes are auditable; a user cannot silently overwrite a selection.

## Acceptance tests

- A customer can buy without a consultation request.
- A visitor cannot enumerate clinics, doctors, zones or contact cards through pages, search or APIs.
- Two eligible partners in one zone result in one policy-selected, logged target.
- A suspended/capped partner is never selected.
- A selected partner receives no customer details without lead-sharing consent.
- A confirmed order keeps its original price after catalogue price changes.
- No-match exposes only the Srasveda escalation contact, not network information.
- A location-mapped request appears in the internal consultation worklist even when no default partner exists, so operations can manually resolve it or use the no-match path.

## Linked records

- [[workflows/WF-CON-001 Consultation Routing]]
- [[domain/Consultation Request]]
- [[domain/Referral]]
- [[domain/Partner Clinic Profile]]
- [[domain/Referral Routing Policy]]
- [[domain/Customer Order]]
