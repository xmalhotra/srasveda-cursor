---
type: screen-spec
id: UI-CUS-001
status: draft
roles: [customer, public]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3
---

# UI-CUS-001 — Customer Home: Shop and Orders

## Job to be done

Help a customer quickly understand available Srasveda products, buy at the displayed approved price, and return to existing orders without making the experience feel like a medical portal.

## Page structure

```text
Header: Srasveda | Profile avatar
Search: in page content (public catalogue only)
Cart / checkout: focused task (back + sticky)

PRODUCTS
  Product row: name, approved descriptor, displayed price → Product

MY ORDERS (signed-in, if orders exist)
  Latest order: status → Order detail

NEED GUIDANCE?
  Request a consultation → private routing (one partner, never a directory)

Bottom navigation: Shop | Orders | Account | More
```

## Behaviour and boundaries

- Public users can browse; authentication is requested at checkout/order history.
- Product price is fetched from the approved server-side price record; the page never treats a browser price as authoritative.
- Consultation is optional. It begins a private routing request and never opens a clinic directory.
- `Support` creates an internal ticket and opens the official Srasveda WhatsApp account with approved prefilled text.
- Order detail `Request cancel or return` is an in-app after-sales ask. It does not cancel, return, or refund. WhatsApp/message is a second channel into the same admin queue. See [[design/screens/After-sales Request]].
- The home can show only approved product copy/assets/reviews.

## Must not show

- Partner candidates/network map, doctor sales attribution, internal product notes, prices for restricted audiences, or medical claims awaiting approval.

## Designed states

| State | Frame |
| --- | --- |
| Guest shop | [Shop](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3) |
| Returning | [Shop — returning](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-131) |
| Empty catalogue | [Shop — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-209) |
| Loading | [Shop — loading](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-263) |
| Product | [Product](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2053) |
| Cart | [Cart](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2108) |
| Review order | [Review order](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2197) |
| Sign in required | [Review order — sign in](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2238) |
| Order recorded | [Order placed](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2278) |
| Pay | [[design/screens/Payment Checkout]] |
| Order detail | [Order detail](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2498) |
| After-sales | [[design/screens/After-sales Request]] |
| Consultation | [Consultation](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2556) |

## Links

- [[requirements/PRD-001 Product Deck and Product Page]]
- [[requirements/ORD-001 Doctor Attributed Customer Order]]
- [[requirements/CON-001 Consultation Request and Private Partner Routing]]
- [[requirements/ORD-004 Manual After-sales]]
