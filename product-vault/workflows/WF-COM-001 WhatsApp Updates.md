---
id: WF-COM-001
type: workflow
status: draft
requirements: [[requirements/COM-001 WhatsApp Updates]]
---

# WF-COM-001 WhatsApp Updates

```mermaid
flowchart TD
  A[Business event or MR request] --> B[Choose approved template]
  B --> C[Resolve recipient and purpose]
  C --> D{Eligible and within frequency rule?}
  D -- No --> E[Do not send; record reason]
  D -- Yes --> F[Queue server-side WhatsApp request]
  F --> G[Provider sends message]
  G --> H[Record sent/delivered/read/failed callback]
  H --> I[Show communication history beside source record]
```

## Example: doctor after visit

1. MR completes a visit and chooses “Send approved product resource.”
2. System selects the relevant doctor resource template and product link.
3. System checks the doctor’s mobile, communication preference and message cadence.
4. System sends/records the message attempt.
5. The doctor profile timeline shows the resource was sent; the next follow-up remains independently due.
