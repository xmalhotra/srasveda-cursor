---
id: SCN-001
type: end-to-end-scenario
status: draft
---

# SCN-001 — Full Business Simulation

## Purpose

Prove that customer, doctor, MR, delivery handler and admin journeys work together without data leakage, duplicate notifications or unauthorised changes.

## Seeded test personas

- **Admin Asha** — authorised operations/admin.
- **MR Meera** — assigned only to Dr Kavita.
- **Dr Kavita** — pre-provisioned doctor, associated with Clinic East Delhi, with an assigned product/quantity journey.
- **Customer Riya** — self-service phone-OTP customer.
- **Handler Dev** — assigned internal delivery/fulfilment user.
- **Partner Clinic East** — private consultation partner; not visible to other personas.

All names, numbers, products, payments and messages are synthetic test data.

## Scenario A — doctor onboarding, sample and feedback

1. Admin creates Dr Kavita, clinic association, assigned MR and product/quantity sample journey.
2. Doctor verifies test OTP and sees prepared professional workspace.
3. MR sees only Dr Kavita and receives product-introduction task.
4. MR records visit/sample; harness asserts both 7-day and 1-month feedback tasks exist.
5. MR records an allowed feedback outcome; harness asserts audit record and next configured task.
6. A different MR is denied access to Dr Kavita and her tasks.

## Scenario B — doctor stock-restock order and delivery proof

1. Dr Kavita places a restock order.
2. Admin assigns Handler Dev.
3. Handler Dev sees only this assigned order, records authorised delivery checkpoint and uploads synthetic receipt/proof.
4. Dr Kavita sees only her order status and approved receipt/proof.
5. Doctor requests cancellation in the app; harness asserts it is a request only and the order stage is unchanged.
6. Admin accepts/rejects it with reason; harness asserts append-only audit event. Accept of a paid cancel does not create `refunded` until ops records payout.
7. Handler Dev is denied price change/cancellation and cannot open an unassigned order.

## Scenario C — customer direct order, payment, delivery and WhatsApp

1. Customer Riya signs up by test OTP and places a direct customer order.
2. Payment simulator sends verified callback twice; harness asserts exactly one payment-confirmed event.
3. Admin/handler progresses packed → dispatched → delivered with synthetic proof.
4. WhatsApp simulator asserts one approved utility-template event per eligible order status; duplicate provider/webhook retries do not duplicate messages.
5. WhatsApp send failure is recorded but does not roll back order status.
6. Riya can view only her order timeline; all other personas are denied customer-order details unless permission explicitly allows a limited signal.
7. Riya submits cancel in the app; harness asserts an after-sales request only, an admin action-centre item, and unchanged order stage. A second submit is blocked.
8. Admin reject leaves the order unchanged. Admin accept of a paid cancel does not refund until ops records payout with evidence. A WhatsApp-filed ask uses the same queue.

## Scenario D — private consultation request

1. Riya requests consultation with synthetic East Delhi location.
2. System maps location and shows request only to authorised admin/operations worklist.
3. Admin selects default/private partner or manually assigns the eligible partner.
4. Harness asserts Riya sees one selected contact card only, never candidate list/network data.
5. Partner lead-sharing is denied without recorded consent.

## Scenario E — support and content safety

1. Each persona clicks Support; harness asserts correct route and internal ticket creation.
2. Ticket closure by admin sends no ticket-status message to requester.
3. Content editor replaces a product image in draft; publisher approves/publishes; harness asserts public asset changes without deployment.
4. Unapproved doctor video/review/claim is blocked from public publication.

## Pass criteria

- Every stated action passes for the permitted actor and fails for disallowed actor.
- Database/status/audit events match the specified business transitions.
- No real provider traffic or personal data is used.
- Scenario can run repeatedly from a clean test environment with identical result.
