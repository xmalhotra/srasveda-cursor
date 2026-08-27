---
type: screen-spec
id: UI-MR-003
status: draft
roles: [mr]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-86
---

# UI-MR-003 — Doctor detail

## Job to be done

Before logging a visit, the MR confirms doctor identity, clinic, lifecycle stage and the latest recorded next action, then starts visit capture in one tap.

## Page structure

```text
Header: ‹ Back | Support

Doctor name
Clinic · zone · relationship stage

BEFORE LOGGING A VISIT
  Latest next action
  Assigned MR · active status

Primary: [ Log visit ]

PRODUCT RELATIONSHIP
  Product · sample/feedback state (assigned doctor only)

TIMELINE
  Own completed visits for this doctor

BOTTOM NAVIGATION
  Today | Doctors (active) | Tasks | Activity | More
```

## Behaviour

- `Log visit` opens [[design/screens/MR Log Visit]] only if this doctor is assigned to the signed-in MR.
- Timeline is chronological completed visits (MR-001-R6).
- Product relationship is a factual MR view, not a doctor-facing deck.

## Must not show

Other doctors, other MR task lists, customer orders, partner/network directory, prices, patient/medical data.

## Figma

Drawn on `01 Journeys — Customer MR Doctor` as `UI-MR-003 Doctor detail`.

## Links

- [[requirements/MR-001 Complete Doctor Visit]]
- [[requirements/PRD-002 Doctor Product Relationship]]
- [[design/screens/MR Log Visit]]
