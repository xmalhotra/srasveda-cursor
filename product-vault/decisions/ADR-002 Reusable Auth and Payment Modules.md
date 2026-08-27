---
id: ADR-002
type: architecture-and-product-decision
status: approved
date: 2026-08-27
---

# ADR-002 Reusable Auth and Payment Modules

## Decision

Phone OTP auth and hosted payment are **platform modules**. Srasveda is the first host. A later product should reuse the module with configuration, not a copy of Srasveda screens and doctor/order rules.

Each module has two layers:

| Layer | Lives in | Changes per product |
|---|---|---|
| **Core** | AUTH-CORE / PAY-CORE | Provider, locale, brand tokens, method list, default post-login route |
| **Host adapter** | AUTH-001 / PAY-001 | Roles, workspaces, packing, WhatsApp, restock, doctor pre-provision |

The Figma frames on `06 Auth` and `07 Payment` are the core UX. Product names, role labels and packing copy are host strings, not module logic.

## Why this was not already plug-and-play

The screens are already isolated pages, but the written contracts mixed core with host:

- AUTH-001 is doctor provisioning, customer-default roles and Srasveda workspaces.
- PAY-001 is customer-order packing, WhatsApp and clinic-restock exclusions.

That is correct for Srasveda. It is the wrong seam for reuse.

## Plug contract

A future host supplies:

1. Brand / theme (wordmark, colours, type — already tokenised in Figma).
2. Identity provider for OTP (SMS vendor, country rules).
3. Payment provider (keys, webhook verification, settlement account).
4. Host callbacks: `onSessionIssued`, `onRolesResolved`, `onPaymentResult`.
5. Copy for default role, guest browse, and what happens after pay.

A future host does **not** fork OTP entry, webhook verification, or card/UPI capture. Those stay in the module.

## What must never leak into the core

- Doctor, MR, clinic, sample, or consultation rules.
- Packing, courier, WhatsApp templates.
- A named gateway in UI copy (Razorpay, Stripe, etc.).
- Product-specific default home screens hardcoded in the module.

## Linked records

- [[requirements/AUTH-CORE Phone OTP Session]]
- [[requirements/PAY-CORE Hosted Payment Adapter]]
- [[requirements/AUTH-001 Account Provisioning and Role Activation]]
- [[requirements/PAY-001 Verified Online Payment]]
- [[requirements/DS-CORE Shared UI System]]
- [[decisions/ADR-003 Shared UI System Module]]
