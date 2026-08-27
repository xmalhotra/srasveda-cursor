---
id: ORD-003
title: Customer order lifecycle and WhatsApp status
status: draft
owner: operations-commerce
priority: with-ordering
---

# ORD-003 — Customer Order Lifecycle and WhatsApp Status

## User outcome

A customer can see an accurate order timeline in the app and receives a concise, approved WhatsApp update when a real order checkpoint is completed. Operations can see the underlying event, evidence and delivery outcome.

## Lifecycle

| Stage | Created by | Customer WhatsApp update |
| --- | --- | --- |
| Awaiting payment | Order checkout created | Optional; only if payment-link/reminder policy is approved |
| Payment confirmed | Verified gateway callback/reconciliation | Yes: payment received / order being confirmed |
| Order confirmed | Authorised order acceptance | Yes |
| Packed | Authorised fulfilment action | Yes |
| Dispatched | Courier/tracking or authorised fulfilment action | Yes, with approved tracking link if available |
| Delivered | Courier confirmation or authorised reconciliation | Yes |
| Payment failed/expired | Verified gateway result | Yes where helpful/approved |
| Cancelled | Authorised cancellation after admin accept | Yes, with approved next step |
| Refunded | Authorised admin record after ops has paid the refund | Yes at customer-relevant checkpoints |

An in-app or message **request** is not a stage. It lives on [[domain/After-sales Request]] until admin accepts or rejects. See [[requirements/ORD-004 Manual After-sales]].

## Tracking rules

- Every stage change creates one immutable [[domain/Order Status Event]] with source evidence.
- Customer order history shows a simple timeline and the present stage; admin shows the full event/audit detail.
- Payment status is accepted only after server-side verification of the selected payment provider callback/signature or approved reconciliation.
- A fulfilment/courier integration may create events automatically after it is approved; until then authorised operations users record the relevant checkpoint.

## WhatsApp update rules

- A completed eligible event queues one approved operational template in the existing customer WhatsApp conversation/channel.
- Each template includes: Srasveda identity, customer-safe stage, order reference, relevant next action/tracking link and official support route.
- The event ID/idempotency key prevents duplicate updates when a worker retries or a webhook repeats.
- The app records `queued`, `sent`, `delivered/read if available` or `failed` on [[domain/Communication Event]]. A message failure never rolls back the order stage.
- If the customer has no eligible WhatsApp route, the order timeline remains correct in the app; operations may follow the separately approved fallback process.
- These are operational order messages, not promotional campaigns. They contain no health information or internal notes.

## Permissions

| Role | May see / do |
| --- | --- |
| Customer / dedicated doctor or clinic account | See only its own customer-safe order timeline, receipts and delivery proof; may request cancel/return/support in the app or by message, but cannot alter the order. |
| MR | See only permitted attributed-order signal; cannot alter fulfilment stage by default. |
| Assigned fulfilment/delivery user | See only allocated order(s); update only authorised preparation/delivery checkpoints and upload proof. |
| Operations/admin | Advance authorised stages, assign handlers, decide cancellations/returns/refunds, handle exceptions and view audit/evidence. |

## Acceptance tests

- A verified payment callback creates `payment-confirmed` once, even if delivered twice by the gateway.
- Dispatch cannot be set before an order is confirmed for fulfilment.
- Every visible stage has a timestamp and corresponding event source.
- One completed dispatch event sends at most one WhatsApp status update, even after retry.
- A WhatsApp send failure leaves the order correctly marked as dispatched and appears as a communication failure for operations.
- A customer can view their own timeline but cannot access another customer's order or internal event notes.
- An assigned delivery user cannot open an unassigned order or change its price/cancellation decision.
- A doctor can see only its own order receipts/proof and cannot directly cancel or rewrite the order; an authorised admin must decide the request.
- A customer in-app cancel/return submit creates an after-sales request only; the order stage stays until admin records an authorised event.
- Admin accept of a paid cancel does not refund; `refunded` is appended only after ops records the payout.

## Linked records

- [[workflows/WF-ORD-003 Customer Order Lifecycle]]
- [[domain/Customer Order]]
- [[domain/Order Status Event]]
- [[domain/After-sales Request]]
- [[requirements/ORD-004 Manual After-sales]]
- [[requirements/COM-001 WhatsApp Updates]]
