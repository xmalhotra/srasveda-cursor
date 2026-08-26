---
id: SOC-001
title: Social presence and publishing
status: draft
owner: brand-content-admin
priority: phase-1-links-automation-later
---

# SOC-001 — Social Presence and Publishing

## User outcome

Visitors can find Srasveda’s official Instagram and X profiles and share approved product pages. The brand team can manage those links and prepare approved social content from the same content system; direct API publishing is optional, controlled and introduced only after account connection/approval.

## Phase 1 — no external publishing API required

- Admin manages official Instagram/X links, display labels and footer/contact placement through [[domain/Social Channel]].
- Product and public pages provide approved share actions that link to the canonical page with UTM tracking; they do not expose internal data.
- Admin creates approved social copy/media drafts and can publish manually in the native Instagram/X apps, then records the resulting post URL for history.
- Website may show a curated, admin-selected “Follow Srasveda” area or approved selected post cards. Do not embed an uncontrolled live feed on the homepage.

## Two approved editorial streams

### Ayurveda and official initiatives

- An editor monitors a small approved source register, initially official Ministry of Ayush and CCRAS updates, and selects relevant public initiatives, research/publications, awareness days or schemes.
- Each item stores the original official URL, source/publish date, factual summary, relevance note and reviewer approval before it appears on the website or social channel.
- The public card clearly attributes and links to the source, for example: `Source: Ministry of Ayush` or `Source: CCRAS`.
- Srasveda adds only a neutral contextual note such as “sharing an official Ayurveda update”; it does not rewrite an initiative as a product endorsement or treatment recommendation.

### Srasveda in practice

- Publish approved, factual activity updates: product education, staff/clinic learning sessions, community participation, heritage milestones, behind-the-scenes quality/process content and customer-support improvements.
- Each update identifies what happened, when, where, what permission/media rights exist and whether a doctor/clinic/customer identity can be shown.
- Do not expose the partner-clinic network, patient/customer details, private MR activity or unauthorised doctor identities merely to make the social feed look active.

## Later phase — optional connected publishing

- Connect an eligible professional Instagram account through the official Meta/Instagram publishing route, and an X account through authorised X API access.
- Store credentials only server-side; use least-required permissions, explicit connection owner and revocation/disconnect controls.
- Admin creates per-platform draft, selects channels, previews, submits for approval and schedules/publishes. Each channel gets its own result/audit state.
- Failed publishing appears in an internal worklist; the system never retries indefinitely or silently posts duplicates.

## Guardrails

- Social accounts are marketing/public channels, not a substitute for the official WhatsApp support route or order-status system.
- No customer order details, phone numbers, consultation requests, private doctor/clinic data or internal MR information may enter social copy/media.
- Product/health claims, testimonials, doctor references and before/after content require the same approval/permission controls as website content.
- Government initiative content must not use the Government emblem, logo or wording that implies Srasveda is a government partner, recipient, certified/approved business or endorsed product unless documented approval authorises that exact use.
- Government-source links are information references; they are not proof that a Srasveda product treats a condition or is supported by that initiative.
- Use a curated social proof section rather than a live feed, which can introduce unreviewed content, performance issues and third-party tracking.

## Acceptance tests

- An admin changes an official profile URL and it updates the public footer without deployment.
- A product share action sends the visitor to the intended platform/share route with the correct canonical link.
- A social draft cannot be published/scheduled without required approval.
- An API connection token is never returned to the browser or a content-editor role.
- A failed channel publish records failure internally and does not duplicate a successfully published post on another channel.
- An official-initiative card cannot publish without its source URL, source date, attribution and reviewer approval.

## Linked records

- [[workflows/WF-SOC-001 Social Content Publication]]
- [[domain/Social Channel]]
- [[domain/Social Post]]
- [[requirements/CMS-001 Content, Media and Theme Management]]
