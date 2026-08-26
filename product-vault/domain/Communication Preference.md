---
type: domain-object
status: draft
related: [[requirements/COM-001 WhatsApp Updates]]
---

# Communication Preference

Records whether a doctor, customer, distributor or MR may receive a defined class of WhatsApp communication.

## Minimum fields

- recipient type and recipient record;
- verified mobile number;
- channel: WhatsApp;
- purpose: operational, relationship follow-up, product/resource update, marketing;
- consent/permission status and captured date/source;
- opt-out date/reason where applicable;
- preferred language when supported;
- last communication timestamp for frequency controls.

## Guardrails

- Operational and promotional/marketing messages are distinct categories.
- A recipient who opts out of optional updates receives no further optional updates.
- No patient health information, internal MR notes, margins or unapproved product claims may be sent.
- Consent and message-history rules must be reviewed against the selected provider and applicable Indian requirements before launch.
