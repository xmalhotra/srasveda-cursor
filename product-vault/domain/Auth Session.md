---
type: domain-object
status: draft
module: reusable
---

# Auth Session

The device session issued by [[requirements/AUTH-CORE Phone OTP Session]] after a mobile is verified. It is not a role and not a business profile.

## Required fields

- Account, device/session id, issued-at, expires-at or idle policy, revoked-at.
- Authentication method: `phone-otp`.
- Issuer (OTP provider reference) for audit.

## Rules

- A valid session means the mobile was verified. It does not mean doctor, staff or any host privilege.
- Revoke on sign-out of this device. Other devices stay until the host policy says otherwise.
- The host reads roles from [[domain/Account Role Assignment]] (or its own equivalent), not from this object.

## Host adapter

Srasveda maps session → customer / doctor / MR / admin workspaces in [[requirements/AUTH-001 Account Provisioning and Role Activation]].
