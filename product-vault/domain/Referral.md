---
type: domain-object
status: draft
---

# Referral

The controlled link between one [[domain/Consultation Request]] and one selected [[domain/Partner Clinic Profile]].

## Fields and rules

- Stores routing-policy version, internal selection reason and timestamp.
- Stores contact-card-shown time, lead-sharing consent and partner-notification status.
- States: `created`, `contact-shown`, `lead-shared`, `acknowledged`, `closed`, `cancelled`.
- One request has at most one active referral unless an authorised re-route is recorded.
- A partner receives only minimum necessary, explicitly consented lead data; never network, priority, unrelated orders or medical data.
