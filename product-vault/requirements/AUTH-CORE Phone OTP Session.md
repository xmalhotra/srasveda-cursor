---
id: AUTH-CORE
type: feature-contract
status: draft
release: Foundation
owner: platform
roles: [public, signed-in]
module: reusable
workflows: []
domain: [[domain/Auth Session]], [[domain/User Account]]
screens: [[design/screens/Auth Sign in and Sign out]]
tests: [pending]
decisions: [[decisions/ADR-002 Reusable Auth and Payment Modules]]
---

# AUTH-CORE — Phone OTP session

Reusable identity module. It proves control of a mobile number, issues a device session, and ends that session. It does not decide product roles.

## User outcome

A person can sign in with OTP, stay signed in on this device, and sign out. The host product then decides which workspace to open.

## Plug-and-play surface

| Host supplies | Module owns |
|---|---|
| Brand tokens and wordmark via [[requirements/DS-CORE Shared UI System]] | Sign in, OTP, error, expired, verifying, sign out, signed out, blocked |
| OTP SMS provider and country/length rules | Session create / refresh / revoke |
| Default first-account policy (e.g. `customer`) | One-account-per-mobile; conflict → blocked, not merge |
| `resolveAccess(account)` → homes the user may open | No role grant from OTP |
| Guest-continue route (optional public home) | Sign-out does not delete the account |

Swap the host: change provider config, theme, `resolveAccess`, and copy. Do not rewrite OTP screens or session rules.

## Functional requirements

| ID | Requirement | Priority |
|---|---|---|
| AUTH-CORE-R1 | Login identifier is a verified mobile after OTP. Password is out of this module. | Must |
| AUTH-CORE-R2 | OTP is identity only. It never grants a privileged role. | Must |
| AUTH-CORE-R3 | One mobile maps to one account. Conflicts go to host review; the module returns `blocked`. | Must |
| AUTH-CORE-R4 | Sign out revokes this device session only. | Must |
| AUTH-CORE-R5 | Invalid, expired, verifying and resend states are in the module. | Must |

## Events the host must handle

| Event | When | Host does |
|---|---|---|
| `otp.verified` | Code accepted | Load account; call `resolveAccess` |
| `session.issued` | Device session created | Route to the host home or workspace picker |
| `session.blocked` | Conflict or suspension | Show Cannot sign in; host ops queue |
| `session.revoked` | Sign out | Clear client session; optional guest home |

## Out of scope (host adapter)

Doctor pre-provision, role promotion, workspace picker labels, shop vs field vs admin homes. Those are [[requirements/AUTH-001 Account Provisioning and Role Activation]].

## UX contract

Screens on Figma page `06 Auth — Sign in`. Chrome is [[requirements/DS-CORE Shared UI System]]. Product-specific sentences (doctor, shop, packing) are host copy slots on those frames.

## Acceptance scenarios

- Given a new mobile, when OTP succeeds, then a session exists and the host receives `otp.verified` with no privileged role.
- Given a wrong or expired code, when the user submits, then the module stays on OTP and does not issue a session.
- Given sign out, when confirmed, then this device cannot call authenticated APIs until OTP succeeds again.
