---
id: UX-001
title: Role-based application experience
status: draft
owner: product-owner
priority: phase-1
---

# UX-001 — Role-based Application Experience

## Principle

All users enter the same `srasveda.com` application, but see a role-specific home and only the information/actions they need. Shared records do not mean shared visibility.

## Customer home

The customer should see a simple commerce-first experience:

- Browse products, search, product detail, approved price, offers and checkout.
- My orders: payment, fulfilment/delivery status, invoice/support, reorder.
- Optional “Need a consultation?” entry; request status and one selected partner contact only.
- Profile: phone OTP identity, addresses, consent/communication preferences.
- A visible Support action routes to the official Srasveda WhatsApp account with approved prefilled text.

The customer must not see MR details, internal doctor/product notes, price rules, other customer data, partner candidates or the wider clinic network.

## Doctor home

The doctor should see a professional relationship/resource experience, not an internal CRM:

- Relevant approved product resources/decks, ingredients, directions and product-specific updates.
- Their own sample/product discussion history, where approved for display.
- Request/reorder pathway for doctor/clinic needs, discount/reorder links where commercially approved.
- Their dedicated MR’s approved contact and support channel.
- A visible Support action routes to the currently assigned MR.
- Optional professional profile/contact preferences.

The doctor must not see internal priority, sales attribution, other doctors, MR task lists, customer orders or network directory data.

## MR home

The MR should see an action-first field-work workspace, optimised for a phone now and tablet later:

- **Today:** visits, overdue/follow-up tasks, planned route and urgent alerts.
- **My doctors:** only assigned doctors; stage, last interaction, next required action and clinic context.
- **Doctor detail:** affiliation history, product relationship, samples, factual feedback, activity/order signals permitted by policy and timeline.
- **Visit mode:** product deck/presentation, log discussion, sample proposal/issue, next action and due date.
- **Tasks:** automated onboarding, sample-feedback and sales-checkpoint tasks; completion evidence and reasoned exceptions.
- **My performance:** only their own activity/outcomes, with transparent definitions.
- A visible Support action routes to the designated admin/operations support contact.

The MR must not change partner-routing priority, product price, doctor ownership without approval, global records, compliance settings or other MRs’ data.

## Admin / operations home

The admin should oversee the system through exceptions and operational decisions—not just raw data tables:

- **Action centre:** pending doctor onboarding approvals, overdue MR tasks, samples/feedback exceptions, unassigned records, no-match consultation requests, payment/fulfilment exceptions.
- **Network:** doctors, clinic affiliations/history, MR assignments, private partner eligibility and referral caps.
- **Commerce:** products, approved price versions, discount codes, customer/doctor/clinic orders, payment and fulfilment status.
- **Relationship operations:** playbook versions, sales checkpoints, task rules, performance reporting and audited overrides.
- **Consultation routing:** private policy version, eligibility, availability, audit trail and consent-safe referral status; never a public directory.
- **Content/compliance:** product assets/decks, claims/approval state, WhatsApp templates and consent preferences.
- **Content studio:** media library, product content, homepage banners, heritage content and controlled brand-theme settings with draft/review/publish history.
- **Security:** user roles, OTP/access events, audit log and data-retention controls.
- **Support worklist:** internally created support tickets, ownership, notes and manual closure.

## Entry and navigation

- Phone OTP identifies the user; role and permissions decide the home screen. See [[requirements/AUTH-001 Account Provisioning and Role Activation]] for pre-provisioning and role promotion.
- A user with multiple approved roles chooses a workspace after login; access is not inferred from a URL alone.
- Public browsing works without login. Login is requested only for orders, account history, professional resources or internal work.
- Deep links always re-check role/record permissions on the server.

## Acceptance tests

- Each role lands on its own home with no irrelevant navigation item.
- A customer cannot discover a partner directory through search, links, page source or an API.
- An MR sees only currently assigned doctors unless an approved handover policy grants limited history.
- A doctor sees only their own approved professional resources and relationship data.
- Admin exceptions link to the exact record/action required, and the action is audited.

## Linked records

- [[design/Role-based Experience Map]]
- [[domain/Doctor Relationship Playbook]]
- [[requirements/CON-001 Consultation Request and Private Partner Routing]]
- [[requirements/DOR-001 Doctor Onboarding and Relationship Playbook]]
