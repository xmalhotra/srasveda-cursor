---
type: design-map
status: draft
related: [[requirements/UX-001 Role-based Application Experience]]
---

# Role-based Experience Map

## Sign in and sign out

Shared: `Sign in (mobile) → OTP → home or Choose workspace`

`Profile / More / Account → Sign out? → Signed out → Sign in or Continue browsing shop`

OTP identifies the mobile. It does not grant a doctor or staff role. Public shop browsing works without an account.

## Customer

Nav: `Shop | Orders | Account | More`

`Shop → Product → Cart → Review order (OTP if needed) → Place order and pay → hosted provider → confirming → paid or failed`

Optional: `Need a consultation? → area + consent → one selected partner or no-match`

Payment is hosted. The app does not collect card or UPI secrets. Paid is a verified callback.

`Order detail → Request cancel or return → request received (order unchanged) → admin decides`

WhatsApp/message is a second channel into the same admin queue. Refund is recorded after ops has paid it.

## Doctor

Nav: `Resources | Orders | Support | Profile`

`Resources → Resource detail → Request restock → Orders / receipt timeline → Request cancel or return (admin decides) → Support (dedicated MR)`

Same mobile can open the customer shop when that workspace is active.

## MR

Nav: `Today | Doctors | Tasks | More`

`Today → Doctor detail → Log visit → sample/feedback → next required task`

## Admin / operations

Nav: `Home | Network | Commerce | More`

`Action centre → exact record (approve / assign / reject with reason) → audit stays`

After-sales: accept/reject the request, then record refund after payout. In-app and WhatsApp asks are the same queue.

Network starts doctor onboarding. Commerce holds order exceptions. More holds Content studio, consultation routing, support and security.

## Design rules

- Shared chrome comes from [[requirements/DS-CORE Shared UI System]]. Role workspaces compose it; they do not copy it.
- Customer: warm, simple, purchase-oriented, minimal medical language.
- Doctor: professional, resource-oriented, no CRM mechanics.
- MR: large tap targets, offline-resilient later, action-first; deck works in tablet presentation mode.
- Admin: dense but calm operations workspace; every exception has an owner, next action and audit trail.
- Public/network-sensitive information is never placed in a client-side navigation payload simply because a role cannot see its menu item.

## First-screen specifications

- [[design/screens/Auth Sign in and Sign out]]
- [[design/screens/Payment Checkout]]
- [[design/screens/MR Home — Today]]
- [[design/screens/MR My Doctors]]
- [[design/screens/MR Doctor Detail]]
- [[design/screens/MR Log Visit]]
- [[design/screens/Customer Home — Shop and Orders]]
- [[design/screens/Doctor Home — Professional Resources]]
- [[design/screens/Admin Home — Action Centre]]
- [[design/screens/After-sales Request]]
- [[design/screens/DS-CORE Shared UI]]
- [[requirements/DS-CORE Shared UI System]]
