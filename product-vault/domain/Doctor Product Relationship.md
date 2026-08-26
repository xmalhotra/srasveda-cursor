---
type: relationship-object
status: draft
from: [[domain/Doctor]]
to: [[domain/Product]]
---

# Doctor–Product Relationship

Tracks the doctor’s business/product journey without calling it a clinical endorsement.

## Suggested states

`Not introduced → Discussed → Interested → Sample given → Feedback due → Feedback recorded → First order → Regular order → Paused / not interested`

## Required fields

- doctor and product;
- current relationship state and state date;
- first/last discussion, sample and order links;
- next product action and due date;
- responsible MR at the time of action;
- concise internal feedback tags/notes; and
- product suitability/interest tags only if approved as non-clinical business segmentation.

## Guardrail

This record may guide MR follow-up and product education. It must not generate patient-specific treatment or prescription advice.
