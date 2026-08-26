---
type: domain-object
status: draft
related: [[requirements/COM-001 WhatsApp Updates]], [[domain/Communication Preference]]
---

# Communication Event

An auditable attempt to send an approved WhatsApp update.

## Minimum fields

- recipient and mobile number used;
- purpose and template/version;
- source record: visit, sample, follow-up, order, payment, fulfilment or consultation referral;
- requested/sent/delivered/read/failed status where provider supplies it;
- provider message reference;
- created by: system, MR or admin;
- failure reason/retry status;
- content snapshot or approved template parameters, subject to retention policy.

## Rule

WhatsApp delivery does not replace a business record. The visit, order, payment or follow-up remains the system of record; the communication event only records the outreach.

Consultation messages contain only the selected contact card or neutral status updates, never health details.
