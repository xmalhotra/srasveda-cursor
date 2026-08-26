---
type: domain-object
status: draft
---

# Sales Checkpoint

A versioned, non-clinical commercial rule that evaluates the attributable order activity linked to a doctor and creates the next appropriate MR task.

## Examples

- No qualifying order within 21 days after recorded sample feedback → follow-up task.
- First qualifying order → thank-you/relationship review task.
- Second order within 60 days → regular-order review task.
- No repeat order within 90 days after activation → re-engagement task.

The numbers above are examples, not approved business policy.

## Guardrails

- “Qualifying sale” must explicitly state included channels, order states, value/quantity threshold and attribution rule.
- Checkpoints use completed/confirmed business events, not an MR's informal claim.
- The rule records the source orders and evaluated version so results are explainable.
- It creates an [[domain/Automated MR Task]]; it does not change doctor status without the approved rule and human review where required.
