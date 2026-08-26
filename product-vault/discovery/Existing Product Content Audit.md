---
type: discovery-audit
status: active
source: existing-srasveda-nextjs-project
reviewed: 2026-08-09
---

# Existing Product Content Audit

## What already exists

The current Next.js source is a valuable catalogue seed, not a throwaway prototype.

| Available now | Location | Reuse status |
| --- | --- | --- |
| 23 product records | `lib/products.ts` | Import as draft product records; verify every field before publication |
| Product names/categories, descriptions, benefit bullets, ingredients, suggested usage and FAQs | `lib/products.ts` | Source material only; claims require review |
| Product image files | `public/images/products/` | Import into managed media library; attach rights/alt text/approved primary image |
| Public product listing/detail pages | `app/products/`, `app/products/[slug]/` | Good layout reference; replace static data with governed catalogue later |
| Privacy policy | `app/privacy-policy/page.tsx` | Starting copy; replace/extend before new app launch |
| Terms | `app/terms/page.tsx` | Starting copy; replace/extend before direct checkout launch |
| Brand/manufacturer/contact details | `lib/constants.ts` | Verify as current authoritative business details |

## Data still missing per purchasable SKU

- Regulatory classification and evidence for that classification.
- Exact SKU/variant/pack size/net quantity and current stock/active status.
- Approved price, tax treatment, price effective dates and allowed audience.
- Manufacturer details and applicable licence/reference evidence for the specific SKU.
- Batch/expiry/label source where operationally needed; storage, warnings/contraindications and exact approved directions.
- Country of origin where applicable, product owner, review date and approval history.
- Public/professional/internal audience boundary and approved source assets/decks.

## Claims needing review before reuse

In the current source, product copy uses phrases such as `Useful in…`, `Supports…`, `Increases…`, named diseases/conditions, fertility/conception outcomes and symptom/treatment-style descriptions. These are **claims**: statements that a product treats, prevents, mitigates, improves or otherwise affects a condition/body function.

They appear in more than one place:

- product short description and main description;
- benefit bullets;
- product FAQs;
- page metadata/Open Graph descriptions;
- testimonials/review-style text;
- category names/marketing headings where they imply a medical outcome.

Do not solve this by merely replacing every phrase with `supports`. The responsible owner must decide, per SKU/category, whether the statement is permitted, evidence-backed, correctly classified and appropriate for public versus doctor-only content.

## Current testimonial issue

The existing product records contain repeated generic “Verified SRAS Veda customer” testimonials. These must **not** migrate as verified reviews: there is no linked delivered order, customer identity/consent, date or moderation record. Replace them with the controlled review/story model in [[requirements/REV-001 Reviews and Credibility Evidence]].

## Content/regulatory approver: what it means

This is the named person responsible for saying “this exact information may go live” for each product.

Recommended separation:

| Role | Responsibility |
| --- | --- |
| Content editor | Prepares image, copy, FAQ, deck and social/WhatsApp draft. |
| Product/regulatory approver | Checks SKU classification, label/manufacturer/licence evidence, ingredients, usage/warnings and every product/health claim. |
| Publisher | Makes an approved version live; cannot self-approve sensitive material unless explicitly authorised. |

Dr Neeru Malhotra may be an appropriate product/clinical-content authority if she is empowered for this role, but founder/expert status alone should not be assumed to cover legal/regulatory approval. Record the appointed person(s) and their scope.

## Suggested review cadence to approve or change

- Before first public launch of every SKU: full review.
- Any change to claims, ingredients, directions, warnings, classification, manufacturer/licence information or professional deck: review before publish.
- Price/image/ordinary marketing copy: appropriate content/publisher review before publish.
- Scheduled full SKU review: every 12 months, and immediately if label/manufacturer/regulatory facts change.

## Policy structure to adapt, not copy

The existing legal pages are useful starters, but they currently assume WhatsApp order confirmation and generic policy wording. The new direct-commerce flow needs plain, Srasveda-specific policies for:

- Privacy: identity/contact of the data controller, data collected, purpose, operational partners, retention, rights/contact, WhatsApp and consultation consent, and no unnecessary health-data intake.
- Shipping: delivery areas, charge, expected dispatch/delivery windows, internal delivery proof and support path.
- Returns/cancellation: eligibility, sealed/opened/damaged-product rule, cancellation cut-off, request method, refund method/timing and exceptions.
- Terms: web checkout/payment, order acceptance, current price/tax, delivery, support and product-information boundaries.

Himalaya publicly separates shipping, returns/cancellation, terms and privacy, and its product pages show price, ingredients, directions and manufacturer information. Kama Ayurveda similarly has separate delivery/return/support flows. Use this structure as a benchmark; do not copy their wording or their commercial periods/charges. See [Himalaya transaction/policy links](https://himalayawellness.in/pages/transaction), [Himalaya shipping policy](https://himalayawellness.in/policies/shipping-policy), [Kama Ayurveda returns policy](https://www.kamaayurveda.com/uk/en_GB/returns-and-refunds-policy).

## Next intake task

Create a product intake sheet for each SKU by importing existing data as `draft`, attaching pack-label/manufacturer/licence evidence, assigning classification/approver, and approving the public/professional copy field by field. No code or deployment is needed to begin this work.
