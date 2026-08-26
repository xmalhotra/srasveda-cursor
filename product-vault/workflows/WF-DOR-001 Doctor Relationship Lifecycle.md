---
id: WF-DOR-001
status: draft
---

# WF-DOR-001 — Doctor Relationship Lifecycle

```mermaid
flowchart TD
  A[MR identifies doctor] --> B[Complete qualification checklist]
  B --> C{Admin/owner approves onboarding?}
  C -- No --> D[Keep candidate; resolve missing evidence]
  C -- Yes --> E[Assign playbook and primary MR]
  E --> F[Automated task: product introduction]
  F --> G[MR logs visit and product discussion]
  G --> H{Sample approved/issued?}
  H -- Yes --> I[Create feedback tasks: 7 days and 1 month]
  H -- No --> J[Create configured next follow-up task]
  I --> K[MR records outcome at each feedback checkpoint]
  J --> K
  K --> L[Evaluate confirmed attributable order checkpoints]
  L --> M[Create next task: first-sale review, growth review or re-engagement]
  M --> N[MR completes action; lifecycle repeats]
```

Every automated task stores the originating playbook/checkpoint version and evidence. Automation proposes and tracks work; people record real-world facts.
