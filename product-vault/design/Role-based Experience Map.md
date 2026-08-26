---
type: design-map
status: draft
related: [[requirements/UX-001 Role-based Application Experience]]
---

# Role-based Experience Map

## Customer

`Home → Products → Product detail → Cart / Checkout → My orders / Reorder`

Optional support path: `Need a consultation? → zone + consent → one selected partner contact → request status`

## Doctor

`Professional home → Product resources → My product discussions/samples → Reorder or request → Contact dedicated MR`

## MR

`Today → My tasks → Doctor detail → Visit mode → sample/feedback → next required task`

## Admin / operations

`Action centre → Network → Commerce → Relationship operations → Consultation routing → Content/compliance → Security`

## Design rules

- Customer: warm, simple, purchase-oriented, minimal medical language.
- Doctor: professional, resource-oriented, no CRM mechanics.
- MR: large tap targets, offline-resilient later, action-first; deck works in tablet presentation mode.
- Admin: dense but calm operations workspace; every exception has an owner, next action and audit trail.
- Public/network-sensitive information is never placed in a client-side navigation payload simply because a role cannot see its menu item.

## First-screen specifications

- [[design/screens/MR Home — Today]]
- [[design/screens/Customer Home — Shop and Orders]]
- [[design/screens/Doctor Home — Professional Resources]]
- [[design/screens/Admin Home — Action Centre]]
