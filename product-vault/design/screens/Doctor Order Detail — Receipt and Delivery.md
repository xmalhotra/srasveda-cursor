---
type: screen-spec
id: UI-DOC-002
status: draft
roles: [doctor]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-518
---

# UI-DOC-002 — Doctor Order Detail: Receipt and Delivery

## Purpose

Let a doctor view their own restock order and its receipts/proof without exposing internal operations or allowing uncontrolled changes.

```text
Order #[reference]                         Current status: Delivered
Clinic / delivery location (approved view)

Items and approved order total
Order receipt                               [View / Download]
Delivery timeline: confirmed → packed → delivered
Delivery receipt / proof                    [View]

Need help with this order?                  [Support] (MR / WhatsApp)
Request cancel or return                    [Request]
```

## Boundaries

- The doctor sees only their own order and customer-safe receipt/proof.
- There are no edit-price, edit-item, edit-status, edit-handler or direct-cancel controls.
- `Request cancel or return` creates an [[domain/After-sales Request]] for authorised admin review. It does not cancel or refund. The same queue is used if the ask arrived by message. See [[design/screens/After-sales Request]].

## Designed states

| State | Frame |
| --- | --- |
| Orders list | [Orders](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-354) |
| Empty | [Orders — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-464) |
| Order detail | [Order detail](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-518) |
| After-sales | [[design/screens/After-sales Request]] |
| Request restock | [Request restock](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-526) |
| Validation | [Request restock — error](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-574) |
| Submitted | [Request restock — submitted](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-621) |
