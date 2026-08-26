---
id: CMS-001
title: Content, media and theme management
status: draft
owner: brand-content-admin
priority: foundation
---

# CMS-001 — Content, Media and Theme Management

## User outcome

An authorised Srasveda admin updates product photos, decks, approved copy, homepage/heritage content and limited brand settings from the dashboard. Publishing makes the approved change live without a code build or deployment.

## Dashboard capabilities

- Upload/manage [[domain/Media Asset]] files and assign them to product/gallery/deck/banner roles.
- Replace primary product image, reorder gallery images, edit alt text and preview mobile/desktop presentation.
- Edit product/page/FAQ/heritage/banner content fields.
- Manage restricted [[domain/Theme Setting]] values: logo, named colours, banner, selected font and footer/contact content.
- Reuse approved product assets and copy in a draft [[domain/Social Post]] where social publishing is enabled.
- Save draft, submit for review, approve/publish, urgently unpublish and roll back to a prior approved version.
- Show where an asset/content item is used before replacement or archive.
- Provide a single per-SKU **Product Workspace** with all draft, evidence, approval and publication fields in one place. See [[design/screens/Admin Product Workspace]].

## Product Workspace tabs

| Tab | Admin manages | Approval boundary |
| --- | --- | --- |
| Overview | Product name, internal SKU, pack/variant, status, owner and review date | Product owner approval |
| Classification & evidence | Regulatory category, manufacturer, licence/reference files, label/pack proof and source notes | Product/regulatory approver required |
| Commercial | MRP/selling price, tax treatment, price effective date, stock/availability and audience rule | Authorised commercial/admin approval required |
| Public product content | Name, short description, approved public copy, ingredients, directions, warnings, storage, FAQs and SEO metadata | Product/regulatory approver required for regulated facts/claims |
| Professional / MR resources | Doctor deck, MR presentation, internal sample guidance and audience visibility | Product owner + relevant compliance approval |
| Claims | Every statement that describes a benefit, outcome, condition, body function or comparative/safety promise, with evidence/source and permitted audience | Product/regulatory approver required; no self-publish |
| Media | Pack shots, gallery, label photos, PDFs/videos, alt text, rights/source and use locations | Content approval; claim-bearing media needs stricter review |
| Reviews & perspectives | Moderated customer reviews, customer stories and approved professional perspectives | Consent/moderation/compliance approval required |
| History | Draft versions, approvals, publication dates, changes, rollback and urgent unpublish | Read-only audit trail |

## Publication rules

- Ordinary photo/copy/theme updates publish through [[domain/Content Publication]] and revalidate affected pages/CDN cache; no code deployment is required.
- Product claims, ingredients, regulatory facts, doctor quotes/logos and public reviews require their designated approval before publication.
- Admins cannot publish arbitrary JavaScript, CSS, tracking scripts or a new page layout through this system.
- A code/design deployment remains required for a new feature, page type, checkout behaviour or design component.

## Permissions

| Role | May do |
| --- | --- |
| Content editor | Create/edit drafts and upload assets. |
| Reviewer/compliance | Approve/reject regulated product/claim content. |
| Publisher/admin | Publish, unpublish and roll back authorised content. |
| Developer | Change components, schema and platform behaviour through code review/deployment. |

## Acceptance tests

- An editor replaces a product photo, previews it and an authorised publisher makes it live without deployment.
- The old published image remains recoverable through version history.
- Draft/unapproved claim content cannot appear publicly.
- Changed product imagery refreshes affected views within the configured cache window.
- Theme settings reject invalid values and arbitrary code.

## Linked records

- [[workflows/WF-CMS-001 Publish Content Change]]
- [[domain/Media Asset]]
- [[domain/Content Publication]]
- [[domain/Theme Setting]]
