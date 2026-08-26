---
id: ADR-001
type: architecture-and-product-decision
status: approved
date: 2026-08-08
---

# ADR-001 Version One Boundary

## Decision

Phase 1 prioritises the internal MR/admin relationship workflow: doctor directory, product presentation, visits, samples and follow-ups. The platform remains a responsive web app at `srasveda.com`. Customer/doctor order and discount-code flows are core domain specifications now; their implementation phase is pending operational validation.

## Included

- MR phone/tablet use;
- public product education;
- admin management of doctors, MRs and product resources;
- phone OTP as primary authentication design;
- WhatsApp as a tracked, template-based update layer for approved regular communications;
- no patient medical records.

## Deferred

- mandatory doctor login;
- distributor portal;
- payment gateway and online checkout;
- consumer ecommerce/loyalty;
- native mobile apps;
- advanced inventory/accounting.

## Reason

The existing revenue engine is field-led doctor engagement. The first digital value is improving follow-up consistency and product education for two MRs, not building a consumer marketplace.
