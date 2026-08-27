---
id: ADR-003
type: architecture-and-product-decision
status: approved
date: 2026-08-27
---

# ADR-003 Shared UI system is a platform module

## Decision

The shared chrome — tokens, Button, Field, Icon, Navigation, App bar, Status badge, Content row, Inline alert, Sticky action, Product card, and the mobile shell rules — is its own reusable module: [[requirements/DS-CORE Shared UI System]].

It is not a catch-all `utils` folder, and it is not owned by MR because Phase 1 designed it first. Auth, Payment, Customer, Doctor, MR and Admin **import DS-CORE**. They do not copy it.

Srasveda is the first host. A later product binds new brand tokens and may add documented variants. It does not fork the primitives.

## Layers

| Layer | Lives in | Changes per product |
|---|---|---|
| **Core** | DS-CORE | Component behaviour, layout chrome, token slots, accessibility targets |
| **Host bind** | Theme values + CMS-001 named colours | Cream/forest/sage (or another brand), wordmark font, role nav destinations |
| **Role screens** | Customer / Doctor / MR / Admin / Auth / Payment modules | Page composition only |

## What must never happen

- Copy Button/Field into a role module “to tweak it”.
- Auth or Payment cores invent their own chrome.
- Admin theme settings creating new component types (that stays a code/design change).
- Role modules reaching into another role’s private screens to reuse a primitive — they go to DS-CORE instead.

## Linked records

- [[requirements/DS-CORE Shared UI System]]
- [[requirements/ENG-001 Feature Harness and Scenario Testing]]
- [[decisions/ADR-002 Reusable Auth and Payment Modules]]
- [[design/Figma Wireframe Inventory]]
