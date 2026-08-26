---
type: domain-object
status: draft
---

# Social Post

A versioned social-content draft, reusable across one or more approved [[domain/Social Channel]] records.

## Fields

- Copy per platform, approved media assets, link/UTM target and linked product/page where relevant.
- Content stream: `official-initiative`, `srasveda-activity`, `product`, `heritage` or `other-approved`.
- For an `official-initiative`: original source organisation, source URL, source date, factual summary and attribution label.
- For a `srasveda-activity`: event date/location, factual activity description, media permissions and allowed identities.
- Audience/category, owner, approval status and planned publish time.
- Per-channel result: `draft`, `approved`, `scheduled`, `published`, `failed`, `cancelled`; platform post URL/ID and failure reason.

## Rules

- Public product/health content follows the same approval rules as the website; each channel can require its own copy/asset review.
- A post is not published merely because it is created in the dashboard.
- Publishing attempts are idempotent/auditable to avoid duplicate posts.
- Social post creation does not create a customer WhatsApp message or expose private doctor/clinic network information.
- An official-source post may link to the original source but must not imply the source endorses Srasveda or any product.
