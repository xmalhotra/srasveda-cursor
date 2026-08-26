---
id: AUTH-001
title: Account provisioning and role activation
status: draft
owner: operations-admin
priority: foundation
---

# AUTH-001 — Account Provisioning and Role Activation

## User outcome

Srasveda can prepare a doctor's account and journey before the doctor first logs in. A person who signs up independently is safe by default as a customer; an authorised admin can later verify and promote/link that same account to the doctor profile without losing their customer data.

## Path A — admin pre-provisions a doctor

1. Admin creates/approves [[domain/Doctor]], clinic affiliation, MR assignment and [[domain/Doctor Journey Assignment]].
2. Admin enters the doctor’s approved mobile number and creates a `pre-provisioned` [[domain/User Account]] with a pending doctor-role assignment.
3. The system does not grant doctor access or send unapproved outreach merely because the record exists.
4. On first successful OTP login with that exact mobile, the account activates and the pre-configured doctor workspace is available.
5. Admin/operations can see activation status; the doctor sees only their approved professional workspace.

## Path B — person signs up before admin

1. A person verifies their mobile by OTP.
2. If there is no matching pre-provisioned account, the system creates/activates a customer account only.
3. Admin later creates or identifies the doctor profile and starts `promote/link account`.
4. Admin verifies identity using the approved business process, selects the existing account, and grants a doctor role linked to that profile.
5. Existing customer orders/account history remain on the same account. At the next permission refresh/login, the person can choose their customer or doctor workspace where both are active.

## Conflict handling

- If the same mobile is already associated with another doctor profile, MR, admin or a conflicting pre-provisioned record, block automatic promotion and create an admin review item.
- Never merge accounts, transfer orders or alter a role automatically just because names/phone numbers look similar.
- An admin may correct a mobile/profile link only with reason, evidence and audit entry.

## Permissions

| Action | Authorised role |
| --- | --- |
| Self-service customer registration via OTP | Public/customer flow |
| Create pre-provisioned doctor profile/account | Operations/admin with doctor-onboarding permission |
| Grant/revoke doctor role or link existing account | Authorised admin; verified evidence required |
| View/resolve identity conflicts | Restricted operations/admin |
| View another user's account/roles | Restricted operations/admin only |

## Acceptance tests

- A pre-provisioned doctor who verifies the matching mobile sees their prepared doctor workspace on first login.
- A self-service new OTP user gets only customer access by default.
- An authorised admin can promote/link the existing customer account to a verified doctor profile without creating duplicate orders or accounts.
- OTP alone cannot turn a customer into a doctor.
- A duplicate/conflicting mobile blocks automated linking and enters an auditable review state.
- Revoking doctor access removes that workspace without silently deleting permitted customer order history.

## Linked records

- [[workflows/WF-AUTH-001 Account Provisioning and Role Activation]]
- [[domain/User Account]]
- [[domain/Account Role Assignment]]
- [[domain/Doctor Journey Assignment]]
