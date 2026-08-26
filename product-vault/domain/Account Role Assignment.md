---
type: domain-object
status: draft
---

# Account Role Assignment

An effective-dated, auditable authorisation linking a [[domain/User Account]] to a customer, doctor, MR, distributor/fulfilment or admin workspace.

## Required fields

- Account, role, linked business profile, status and effective date.
- Granting admin, verification method/evidence and approval reference.
- Revocation/suspension reason and audit timestamps.

## Rules

- A doctor role must link to one verified [[domain/Doctor]] profile; phone OTP alone cannot grant this role.
- Promoting a self-service customer account to doctor role links the existing account to the doctor profile rather than creating another account/order history.
- If a pre-provisioned doctor profile and customer account share the same verified mobile, an authorised admin links/promotes after identity verification.
- The role assignment controls server-side access; hiding menu items is not a security control.
