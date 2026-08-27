---
type: screen-spec
id: UI-ORD-004
status: draft
roles: [customer, doctor, admin]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1001
---

# UI-ORD-004 — After-sales request

## Job to be done

Let the customer (or doctor) ask to cancel, return, or get help on **their** order in the app. WhatsApp/message remains a second channel. Every decision and refund stays in admin.

## Customer / doctor

```text
Order detail
  [Request cancel or return]     does not change the order
  Help / Support                 still opens the official message route

Request
  Type: Cancel | Return | Something else
  Note (optional)
  [Submit request]

Submitted
  We have the request. Srasveda will review it.
  The order is unchanged until operations decide.
```

## Admin

```text
Action centre / Commerce → Cancel or return request
  Channel shown: In-app or WhatsApp

[Reject]  reason required — order unchanged
[Accept]  authorised event only — does not pay money

If payout is due:
  Record refund   amount, method, evidence, date
  [Refund recorded]
```

## Must not

- Instant cancel, instant refund, or a customer “refund” button that calls the gateway.
- Show internal notes, ticket IDs, or other customers’ requests.
- Close a request because a message arrived or time elapsed.

## Designed states

| State | Frame |
| --- | --- |
| Customer order (entry) | [Order detail](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2498) |
| Customer request | [Request on order](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1001) |
| Customer submitted | [Request sent](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1057) |
| Customer pending | [Order — request pending](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1087) |
| Duplicate blocked | [Already in review](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1148) |
| Doctor request | [Request on order](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4345) |
| Doctor submitted | [Request sent](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4401) |
| Doctor pending | [Order — request pending](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4467) |
| Admin in-app review | [Cancellation review](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3310) |
| Admin from message | [Cancellation — from message](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4546) |
| Admin return | [Return review](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4602) |
| Admin refund | [Record refund](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4658) |

## Links

- [[requirements/ORD-004 Manual After-sales]]
- [[design/screens/Admin Home — Action Centre]]
- [[design/screens/Customer Home — Shop and Orders]]
- [[design/screens/Doctor Order Detail — Receipt and Delivery]]
