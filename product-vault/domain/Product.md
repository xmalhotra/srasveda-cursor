---
type: domain-object
status: draft
related: [[domain/Product Deck]], [[domain/Product Price]], [[domain/Doctor Product Relationship]], [[domain/Product Feedback]]
---

# Product / SKU

A product is a governed commercial and content entity—not merely a name shown when issuing a sample.

## Product record

- product name, SKU, pack/variant and active status;
- product category and **regulatory classification per SKU**;
- manufacturer and applicable licence/reference records;
- approved public, professional and internal claims/content;
- ingredient/composition list, directions, storage, warnings and pack information;
- associated images, videos, PDFs and deck sections;
- price records; and
- product-content owner, approval state and review date.

## Admin workspace rule

Every field above is edited in the per-SKU Product Workspace as a draft and carries its own source/evidence where relevant. A product may be `draft`, `review`, `active` or `archived`; `active` does not override a pending claim/licence/content review.

Routine product images, decks and page content are versioned [[domain/Content Publication]] records; replacing a photo does not require a code deployment.

## Classification guardrail

Classification must be explicit and approved for every SKU before publication. Do not treat “Ayurvedic medicine” and “wellness/Ayurveda Aahara” as interchangeable labels: FSSAI’s Ayurveda Aahara framework excludes Ayurvedic drugs/proprietary Ayurvedic medicines, and its 2026 notice says a product should be categorised under one applicable category rather than sold with both FSSAI and AYUSH licence numbers. See [FSSAI regulations](https://www.fssai.gov.in/food-law/regulations) and [FSSAI notice](https://westregion.fssai.gov.in/pdf/public-notice/Public-Notice-5-2026.pdf).
