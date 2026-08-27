---
type: screen-spec
id: UI-PAY-001
status: draft
roles: [customer, admin]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1003
---

# UI-PAY-001 — Payment checkout

## Job to be done

Let a customer pay the stored order amount on an approved hosted checkout, then show only a status Srasveda can prove.

## Module vs host

| Core (reuse) | This product |
|---|---|
| Intent, hosted redirect, confirming, results, reconcile | Customer order, packing, WhatsApp, pay-later vs restock |
| No card/UPI secrets in-app | Amount = order price snapshot |

Reuse: keep page `07 Payment` and [[requirements/PAY-CORE Hosted Payment Adapter]]. Swap provider, currency, payable type, and post-pay host screen.

See [[decisions/ADR-002 Reusable Auth and Payment Modules]].

## Flow

```text
Review order → Place order and pay
  → Pay (choose UPI / Card / Net banking)
  → Opening secure payment
  → Provider page (not designed here)
  → Confirming payment (wait for verified result)
  → Payment confirmed
     or failed / cancelled / expired
     or still pending (refresh, do not double-pay)

Pay later → order remains awaiting payment → Pay now from the order
```

Admin: `Payment unconfirmed` exception → record verified event with evidence.

## Behaviour

- Methods open the same approved provider. This app never hosts card or UPI PIN fields.
- Confirming is not a receipt. Paid appears only after a verified callback.
- Failed/cancelled/expired keep the order awaiting payment at the same snapshot.
- Clinic restock is out of scope.

## Designed states

| State | Frame |
| --- | --- |
| Choose method | [Pay](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1003) |
| No method | [Pay — no method](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1071) |
| Opening provider | [Opening payment](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1130) |
| Confirming | [Confirming payment](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1166) |
| Still pending | [Confirming — still pending](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=58-488) |
| Confirmed | [Payment confirmed](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-3841) |
| Failed | [Payment failed](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-3902) |
| Cancelled | [Payment cancelled](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-3939) |
| Expired | [Payment expired](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-3976) |
| Pay later | [Pay later](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=58-358) |
| Order awaiting payment | [Order — awaiting payment](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=58-426) |
| Admin reconcile | [Payment not verified](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=58-4095) |

## Links

- [[requirements/PAY-001 Verified Online Payment]]
- [[requirements/ORD-003 Customer Order Lifecycle and WhatsApp Status]]
- [[requirements/PAY-CORE Hosted Payment Adapter]]
- [[decisions/ADR-002 Reusable Auth and Payment Modules]]
