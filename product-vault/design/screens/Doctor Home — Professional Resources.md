---
type: screen-spec
id: UI-DOC-001
status: draft
roles: [doctor]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-3
---

# UI-DOC-001 — Doctor Home: Professional Resources

## Job to be done

Give a doctor quick access to approved product information, their relationship support and legitimate reorder pathways, without exposing internal sales-management mechanics.

## Page structure

```text
Header: Srasveda | Profile avatar
Bottom navigation: Resources | Orders | Support | Profile

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

```

## Behaviour and boundaries

- Professional access uses phone OTP plus admin-approved doctor role/identity.
- Only professional-facing, approved product decks are shown.
- Reorder pathways depend on the approved [[requirements/ORD-002 Doctor Clinic Reorder]] model.
- Dedicated MR contact is current and role-approved; a reassignment updates it prospectively.
- `Support` creates an internal ticket and opens the assigned MR's approved contact route.

## Must not show

- Other doctors/clinics, internal priority or ranking, sales commission/attribution, MR checklist/tasks, customer identities/orders, or the full partner network.

## Designed states

| State | Frame |
| --- | --- |
| Resources | [Resources](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-3) |
| Empty | [Resources — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-135) |
| Pending verification | [Resources — pending](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-203) |
| Loading | [Resources — loading](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-260) |
| No assigned MR | [Resources — no assigned MR](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-927) |
| Resource detail | [Resource detail](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-288) |
| Support | [Support](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-690) |
| Profile | [Profile](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-790) |
| Access denied | [Access denied](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-900) |

## Links

- [[domain/Doctor MR Assignment]]
- [[requirements/PRD-001 Product Deck and Product Page]]
- [[requirements/ORD-002 Doctor Clinic Reorder]]
