---
type: screen-spec
id: UI-AUTH-001
status: draft
roles: [public, customer, doctor, mr, admin]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-4
---

# UI-AUTH-001 — Sign in and sign out

## Job to be done

Prove control of a mobile number with OTP, open only the approved workspace for that account, and end the session on this device without inventing extra identity checks.

## Module vs host

| Core (reuse) | This product |
|---|---|
| Sign in, OTP, errors, sign out, session | Default role = customer; doctor pre-provision; workspace picker labels |
| OTP ≠ role grant | Doctor / MR / admin assignment |

Reuse: keep page `06 Auth` and [[requirements/AUTH-CORE Phone OTP Session]]. Swap brand, OTP vendor, `resolveAccess`, and the host sentences on the frames.

See [[decisions/ADR-002 Reusable Auth and Payment Modules]].

## Flow

```text
Public shop / Orders / Account / staff cold start
  → Sign in (mobile)
  → Enter OTP
  → one of:
      Customer account created → Shop
      Pre-provisioned doctor ready → Professional home
      Multiple approved roles → Choose workspace
      Identity conflict / suspension → Cannot sign in

Profile / More / Account
  → Sign out?
  → Signed out
  → Sign in  or  Continue browsing shop
```

## Page structure — Sign in

```text
Back | Help

Sign in
Use your mobile. New numbers start as a customer account.

Alert: OTP is not a role grant

Mobile number  [Enter 10-digit mobile]

Continue browsing shop

[Send OTP]
```

## Page structure — Sign out

```text
Back | Help

Sign out?
This device loses orders, professional resources and internal work.

Alert: The shop stays public. Cart on this browser is cleared.

Signed in as  [name · current workspace]

Stay signed in

[Sign out]
```

## Behaviour and boundaries

- Phone OTP identifies the user. Role and permissions decide the home. See [[requirements/AUTH-001 Account Provisioning and Role Activation]].
- A self-service first login creates/uses a customer account unless the mobile matches a valid pre-provisioned doctor/staff account.
- OTP alone cannot grant a doctor, MR or admin role.
- A user with more than one approved role chooses a workspace after login. Access is not inferred from a URL.
- Public product browsing works without login. Login is requested for orders, account history, professional resources and internal work.
- Sign out ends the device session. It does not delete the account, orders or doctor profile.
- A conflicting or suspended mobile shows `Cannot sign in` even if the OTP was correct. Operations must resolve it.

## Must not show

- Password, email-as-required-login, social login, or a role picker for roles the account does not have.
- A claim that verifying a mobile makes the person a doctor.
- Other users’ accounts, internal identity-review notes, or a directory of workspaces.

## Designed states

| State | Frame |
| --- | --- |
| Sign in | [Sign in](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-4) |
| Invalid mobile | [Sign in — invalid](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-43) |
| Enter OTP | [Enter OTP](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-77) |
| Wrong code | [Enter OTP — error](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-109) |
| Expired | [Enter OTP — expired](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3423) |
| Verifying | [Enter OTP — verifying](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3453) |
| Choose workspace | [Choose workspace](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3483) |
| First login — doctor | [First login — doctor](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3529) |
| First login — customer | [First login — customer](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3564) |
| Sign out | [Sign out](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3599) |
| Signed out | [Signed out](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3637) |
| Blocked | [Cannot sign in](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3664) |
| MR entry | [MR More](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3691) |

Doctor Profile, Customer Account/More and Admin More already expose `Sign out` and open this confirm screen.

## Links

- [[requirements/AUTH-001 Account Provisioning and Role Activation]]
- [[requirements/UX-001 Role-based Application Experience]]
- [[domain/User Account]]
- [[domain/Account Role Assignment]]
- [[requirements/AUTH-CORE Phone OTP Session]]
- [[decisions/ADR-002 Reusable Auth and Payment Modules]]
