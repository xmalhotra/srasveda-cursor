---
id: DS-CORE
type: feature-contract
status: draft
release: Foundation
owner: platform
roles: [all]
module: reusable
workflows: []
domain: [[domain/Theme Setting]]
screens: [[design/screens/DS-CORE Shared UI]]
tests: [pending]
decisions: [[decisions/ADR-003 Shared UI System Module]]
---

# DS-CORE — Shared UI system

Reusable design-system module. It owns tokens, primitives, and the mobile shell. It does not own a role’s home, an order, or a visit.

## User outcome

Every workspace looks and behaves like one product. Role screens compose this module; they do not restyle from scratch.

## Plug-and-play surface

| Host supplies | Module owns |
|---|---|
| Token values (canvas, primary, sage, ink, muted, rust) | Token slots and contrast rules |
| Wordmark font (host may use a display face on the mark only) | Operational type: Inter (or host equivalent) on UI chrome |
| Role nav destinations and labels | Bottom nav, app bar (Root / Back), sticky action |
| Extra Content row types if the host needs them | Button, Field, Icon, Status badge, Inline alert, Product card |
| CMS-001 named colour overrides | 390×844 shell, 20px page padding, 52px primary, 48px fields, 44px min targets |

Swap the host: bind tokens and nav destinations. Do not duplicate the component set.

## Functional requirements

| ID | Requirement | Priority |
|---|---|---|
| DS-CORE-R1 | Auth, Payment, Customer, Doctor, MR and Admin import this module. They do not copy primitives. | Must |
| DS-CORE-R2 | Role-specific screens stay in the role module. They compose DS-CORE; they do not own Button/Field. | Must |
| DS-CORE-R3 | A later host binds tokens. Component behaviour (states, targets, shell) stays in DS-CORE. | Must |
| DS-CORE-R4 | New component types are a DS-CORE change, not a CMS theme publish. | Must |
| DS-CORE-R5 | Documented variants (e.g. Content row `Product` / `Order` / `Exception`) are extended in DS-CORE, then used by role modules. | Must |

## Source in Figma

Page [`08 DS-CORE — Shared UI`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-2). Masters are in section `DS-CORE — Components`. Catalog screens instance them.

| Set | Notes |
|---|---|
| Button | Primary / secondary / text / danger; default and disabled |
| Field | Label, value, helper; text, select, date |
| Icon | Shared set; hosts bind destinations |
| Navigation item + role bottom navs | MR, Doctor, Customer, Admin |
| App bar | Type = Root / Back |
| Status badge, Content row, Inline alert, Sticky action | Shared |
| Product card | Customer product; still this module |

## Out of scope

OTP session, hosted checkout, MR visit, admin refund, customer cart. Those modules **reference** DS-CORE.

## Package boundary

```text
src/modules/ds-core/
src/modules/auth-core/
src/modules/pay-core/
src/features/<host-feature>/     # customer, doctor, mr, admin, orders, …
```

Dependency: `features/*` and `auth-core` / `pay-core` → `ds-core`. Never the reverse.

## Acceptance scenarios

- Given a Customer screen and an MR screen, when both show a primary button, then it is the same DS-CORE Button with host tokens.
- Given Admin publishes a named colour, when the app renders, then DS-CORE tokens update and no new component type appears.
- Given Doctor needs a new Content row type, when it is added, then it is added in DS-CORE and imported — not cloned inside the doctor feature.

## Linked records

- [[decisions/ADR-003 Shared UI System Module]]
- [[requirements/AUTH-CORE Phone OTP Session]]
- [[requirements/PAY-CORE Hosted Payment Adapter]]
- [[requirements/UX-001 Role-based Application Experience]]
- [[requirements/CMS-001 Content, Media and Theme Management]]
- [[requirements/ENG-001 Feature Harness and Scenario Testing]]
- [[design/screens/DS-CORE Shared UI]]
