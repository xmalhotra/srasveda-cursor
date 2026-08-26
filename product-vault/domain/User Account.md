---
type: domain-object
status: draft
---

# User Account

The authenticated identity created or activated by phone OTP. An account is separate from the business profile it may later be authorised to access.

## States

- `pre-provisioned` — admin created a pending account/profile association; no successful OTP activation yet.
- `active-customer` — self-service OTP identity with customer role only.
- `active-professional` — verified account with doctor and/or another professional role.
- `suspended` — access blocked by authorised action.

## Rules

- Mobile number is a verified login identifier after OTP, not evidence that the person is a doctor.
- A self-service first login creates/uses `active-customer` by default unless it matches a valid pre-provisioned account.
- Roles are additive only through authorised approval. A customer role may remain alongside doctor role if the business approves that model.
- One mobile number must resolve to one account. Duplicate creation is prevented; an ambiguous/conflicting record goes to an admin review queue.
- OTP verification, role grant/revocation, account link/merge and suspension are auditable.
