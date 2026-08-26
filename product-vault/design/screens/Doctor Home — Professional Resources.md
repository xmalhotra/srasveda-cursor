---
type: screen-spec
id: UI-DOC-001
status: draft
roles: [doctor]
---

# UI-DOC-001 — Doctor Home: Professional Resources

## Job to be done

Give a doctor quick access to approved product information, their relationship support and legitimate reorder pathways, without exposing internal sales-management mechanics.

## Page structure

```text
Header: Srasveda Professional | Support | Notifications | Profile

Welcome: Dr [Name] | [Primary clinic, if approved]

FEATURED RESOURCES
  Approved product/resource cards → View professional deck

MY SUPPORT
  Your Srasveda contact: [Dedicated MR] | Call / WhatsApp
  Request a discussion / support

ORDERS & REQUESTS
  Reorder / request supply | Recent request status

OPTIONAL: MY PRODUCT ACTIVITY
  Only approved, factual sample/resource history

Bottom navigation: Resources | Orders | Support | Profile
```

## Behaviour and boundaries

- Professional access uses phone OTP plus admin-approved doctor role/identity.
- Only professional-facing, approved product decks are shown.
- Reorder pathways depend on the approved [[requirements/ORD-002 Doctor Clinic Reorder]] model.
- Dedicated MR contact is current and role-approved; a reassignment updates it prospectively.
- `Support` creates an internal ticket and opens the assigned MR's approved contact route.

## Must not show

- Other doctors/clinics, internal priority or ranking, sales commission/attribution, MR checklist/tasks, customer identities/orders, or the full partner network.

## States to design later

- Pending doctor-role verification; no assigned MR; no eligible resources; no order history.

## Links

- [[domain/Doctor MR Assignment]]
- [[requirements/PRD-001 Product Deck and Product Page]]
- [[requirements/ORD-002 Doctor Clinic Reorder]]
