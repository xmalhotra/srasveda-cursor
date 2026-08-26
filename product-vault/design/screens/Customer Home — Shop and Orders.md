---
type: screen-spec
id: UI-CUS-001
status: draft
roles: [customer, public]
---

# UI-CUS-001 — Customer Home: Shop and Orders

## Job to be done

Help a customer quickly understand available Srasveda products, buy at the displayed approved price, and return to existing orders without making the experience feel like a medical portal.

## Page structure

```text
Header: Srasveda | Search | Cart | Support | Account

Hero: approved brand/product education message
Primary action: Explore products

PRODUCT COLLECTIONS
  Product card: image, name, short approved descriptor, starting/current price, View product

MY ORDERS (shown after login and if orders exist)
  Latest order: status, reorder / view order

NEED GUIDANCE?
  Need a consultation? → private request flow

Footer/navigation: Shop | Orders | Account
```

## Behaviour and boundaries

- Public users can browse; authentication is requested at checkout/order history.
- Product price is fetched from the approved server-side price record; the page never treats a browser price as authoritative.
- Consultation is optional. It begins a private routing request and never opens a clinic directory.
- `Support` creates an internal ticket and opens the official Srasveda WhatsApp account with approved prefilled text.
- The home can show only approved product copy/assets/reviews.

## Must not show

- Partner candidates/network map, doctor sales attribution, internal product notes, prices for restricted audiences, or medical claims awaiting approval.

## States to design later

- First visit; returning customer with active order; no products available; logged-out checkout request.

## Links

- [[requirements/PRD-001 Product Deck and Product Page]]
- [[requirements/ORD-001 Doctor Attributed Customer Order]]
- [[requirements/CON-001 Consultation Request and Private Partner Routing]]
