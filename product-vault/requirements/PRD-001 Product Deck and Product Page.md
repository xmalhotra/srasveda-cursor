---
id: PRD-001
type: feature-contract
status: draft
release: phase-1
roles: [Public, Doctor, MR, Admin]
domain: [[domain/Product]], [[domain/Product Deck]], [[domain/Product Price]], [[domain/Product Feedback]]
screens: [public-product-page-pending, doctor-product-page-pending, mr-presentation-pending]
---

# PRD-001 Product Deck and Product Page

## User outcome

Every active product has a complete, trusted and audience-appropriate product deck that an MR can present, a doctor can review and a public visitor can understand without exposing internal guidance.

## Required capabilities

- Maintain images, pack/variant, ingredients, directions, warnings, category/classification, approved claims and resources per product/SKU.
- Render separate public, doctor and MR views from the same governed content model.
- Show current approved price only to the audience permitted by the relevant price rule.
- Display only moderated/approved customer reviews; keep doctor feedback internal by default.
- Show content version/review state internally; block publishing/sharing when required content is unapproved or expired.
- Allow an MR to share an approved doctor/public link from presentation mode.

## Guardrails

- No product can be published without classification, content owner and review date.
- No internal deck section may appear in public or doctor view.
- No product review/testimonial is public without moderation and consent.
- Price, ingredient and claims changes retain history and approval metadata.

## Open questions

- [ ] What exact product decks, images, PDFs and videos already exist per SKU?
- [ ] Which pricing contexts should be visible to each role?
- [ ] Who is the named content/regulatory approver?
