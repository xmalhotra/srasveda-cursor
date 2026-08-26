---
type: domain-object
status: discovery
related: [[domain/Customer Order]], [[domain/Discount Code]]
---

# Customer

Represents a customer/buyer for ordering and fulfilment. It is not a patient clinical record.

## Minimum data to decide

- name and mobile number;
- delivery contact/address only when fulfilment requires it;
- consent/preference for operational communications;
- order history;
- attributed/referring doctor where applicable.

## Guardrail

Do not add diagnosis, prescription, treatment history or detailed patient-health information to the customer record.
