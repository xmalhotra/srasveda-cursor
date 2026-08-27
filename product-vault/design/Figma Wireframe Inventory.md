# Srasveda Platform — Figma production screens

**Status:** Phases 1–4 designed in one Figma file, same mobile system. Not build approval.

**Figma file:** [Open the file](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF)

## Direction (locked)

- One product: cream canvas, forest primary, sage soft, Inter for operational UI, Cormorant only on the wordmark.
- Shared chrome is [[requirements/DS-CORE Shared UI System]]. Auth (`06`) and payment (`07`) are reusable cores; Srasveda roles/orders are host adapters. See [[decisions/ADR-003 Shared UI System Module]] and [[decisions/ADR-002 Reusable Auth and Payment Modules]].
- Mobile-first 390 × 844. Root screens use 4-tab bottom nav. Focused tasks use back app bar + sticky action (no tabs).
- DS-CORE components live on [`08 DS-CORE — Shared UI`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-2): Button, Field, Icon, Navigation item, App bar, Status badge, Content row, Inline alert, Sticky action, Product card. Role modules import these; they do not copy them.
- Role-specific bottom nav sets only. New row types: Product, Order, Exception. Product card used on customer product detail.
- No unapproved claims. Payment is not collected in the app UI. Consultation never shows a partner directory.

## File structure

1. `00 Overview` — role map
2. `01 Journeys` — earlier structural sketches (reference only)
3. [`02 Admin — Operations`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=1-5) — **Phase 4**
4. [`03 MR — Mobile app`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=15-34) — **Phase 1**
5. [`04 Doctor — Mobile app`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=45-1393) — **Phase 2**
6. [`05 Customer — Mobile app`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=45-1394) — **Phase 3**
7. [`06 Auth — Sign in`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-2) — **shared login / logout**
8. [`07 Payment — Checkout`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1001) — **customer hosted payment**
9. [`08 DS-CORE — Shared UI`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-2) — **shared chrome module**

## Shared chrome

| Role | Bottom nav | Focused tasks |
|---|---|---|
| MR | Today · Doctors · Tasks · More | Visit, sample, feedback, exception |
| Doctor | Resources · Orders · Support · Profile | Resource, restock, order detail |
| Customer | Shop · Orders · Account · More | Product, cart, review order, consultation, request on order, sign in |
| Admin | Home · Network · Commerce · More | Onboarding, cancel/return/refund, product workspace, routing |
| All roles | — | Shared OTP on `06 Auth`. Shared chrome on `08 DS-CORE`. |

## Phase 1 — MR (`03`)

| Frame | Spec | Requirement |
|---|---|---|
| [Today](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=16-19) | [[design/screens/MR Home — Today]] | MR-001 / DOR-001 |
| [Today — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-2) | [[design/screens/MR Home — Today]] | MR-001 |
| [Today — loading](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=29-575) | [[design/screens/MR Home — Today]] | MR-001 |
| [My doctors](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-37) | [[design/screens/MR My Doctors]] | MR-002 |
| [My doctors — no assignment](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=29-576) | [[design/screens/MR My Doctors]] | MR-002 |
| [Doctor detail](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-86) | [[design/screens/MR Doctor Detail]] | MR-001 |
| [Log visit](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-128) | [[design/screens/MR Log Visit]] | MR-001 |
| [Log visit — error](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-180) | [[design/screens/MR Log Visit]] | TEST-MR-001 |
| [Visit — saved](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=29-577) | [[design/screens/MR Log Visit]] | MR-001 |
| [Sample](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-226) | [[design/screens/MR Log Visit]] | DOR-001 / D-07 |
| [7-day feedback](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-271) | [[design/screens/MR Log Visit]] | DOR-001 / D-08 |
| [Exception](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-313) | [[design/screens/MR Log Visit]] | DOR-001 |
| [Access denied](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-358) | [[design/screens/MR Log Visit]] | MR-001 |
| [Offline](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-392) | [[design/screens/MR Log Visit]] | D-10 pending |
| [More](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3691) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |

## Phase 2 — Doctor (`04`)

| Frame | Spec | Requirement |
|---|---|---|
| [Resources](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-3) | [[design/screens/Doctor Home — Professional Resources]] | DOC-001 / PRD-001 |
| [Resources — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-135) | [[design/screens/Doctor Home — Professional Resources]] | DOC-001 |
| [Resources — pending](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-203) | [[design/screens/Doctor Home — Professional Resources]] | AUTH-001 |
| [Resources — loading](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=46-260) | [[design/screens/Doctor Home — Professional Resources]] | DOC-001 |
| [Resources — no assigned MR](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-927) | [[design/screens/Doctor Home — Professional Resources]] | DOC-001 |
| [Resource detail](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-288) | [[design/screens/Doctor Home — Professional Resources]] | PRD-001 |
| [Orders](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-354) | [[design/screens/Doctor Order Detail — Receipt and Delivery]] | ORD-002 |
| [Orders — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-464) | [[design/screens/Doctor Order Detail — Receipt and Delivery]] | ORD-002 |
| [Order detail](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=47-518) | [[design/screens/Doctor Order Detail — Receipt and Delivery]] | ORD-002 |
| [Request on order](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4345) | [[design/screens/After-sales Request]] | ORD-004 |
| [Request sent](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4401) | [[design/screens/After-sales Request]] | ORD-004 |
| [Order — request pending](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4467) | [[design/screens/After-sales Request]] | ORD-004 |
| [Request restock](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-526) | [[design/screens/Doctor Order Detail — Receipt and Delivery]] | ORD-002 |
| [Request restock — error](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-574) | [[design/screens/Doctor Order Detail — Receipt and Delivery]] | ORD-002 |
| [Request restock — submitted](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-621) | [[design/screens/Doctor Order Detail — Receipt and Delivery]] | ORD-002 |
| [Support](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-690) | [[design/screens/Doctor Home — Professional Resources]] | SUP-001 |
| [Profile](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-790) | [[design/screens/Doctor Home — Professional Resources]] | AUTH-001 |
| [Access denied](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=48-900) | [[design/screens/Doctor Home — Professional Resources]] | AUTH-001 |

## Phase 3 — Customer (`05`)

| Frame | Spec | Requirement |
|---|---|---|
| [Shop](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3) | [[design/screens/Customer Home — Shop and Orders]] | PRD-001 / ORD-001 |
| [Shop — returning](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-131) | [[design/screens/Customer Home — Shop and Orders]] | ORD-001 |
| [Shop — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-209) | [[design/screens/Customer Home — Shop and Orders]] | PRD-001 |
| [Shop — loading](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-263) | [[design/screens/Customer Home — Shop and Orders]] | PRD-001 |
| [Product](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2053) | [[design/screens/Customer Home — Shop and Orders]] | PRD-001 |
| [Cart](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2108) | [[design/screens/Customer Home — Shop and Orders]] | ORD-001 |
| [Cart — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2154) | [[design/screens/Customer Home — Shop and Orders]] | ORD-001 |
| [Review order](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2197) | [[design/screens/Customer Home — Shop and Orders]] | ORD-001 / PAY-001 |
| [Review order — sign in](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2238) | [[design/screens/Customer Home — Shop and Orders]] | AUTH-001 |
| [Order placed](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2278) | [[design/screens/Customer Home — Shop and Orders]] | ORD-003 |
| [Orders](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2339) | [[design/screens/Customer Home — Shop and Orders]] | ORD-003 |
| [Orders — empty](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2410) | [[design/screens/Customer Home — Shop and Orders]] | ORD-003 |
| [Orders — signed out](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2453) | [[design/screens/Customer Home — Shop and Orders]] | AUTH-001 |
| [Order detail](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2498) | [[design/screens/Customer Home — Shop and Orders]] | ORD-003 |
| [Request on order](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1001) | [[design/screens/After-sales Request]] | ORD-004 |
| [Request sent](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1057) | [[design/screens/After-sales Request]] | ORD-004 |
| [Order — request pending](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1087) | [[design/screens/After-sales Request]] | ORD-004 |
| [Already in review](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-1148) | [[design/screens/After-sales Request]] | ORD-004 |
| [Consultation](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2556) | [[design/screens/Customer Home — Shop and Orders]] | CON-001 |
| [Consultation — partner](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2593) | [[design/screens/Customer Home — Shop and Orders]] | CON-001 |
| [Consultation — no match](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2630) | [[design/screens/Customer Home — Shop and Orders]] | CON-001 |
| [Account](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2657) | [[design/screens/Customer Home — Shop and Orders]] | AUTH-001 |
| [More](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2741) | [[design/screens/Customer Home — Shop and Orders]] | SUP-001 / PUB-001 |

## Phase 4 — Admin (`02`)

| Frame | Spec | Requirement |
|---|---|---|
| [Action centre](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2815) | [[design/screens/Admin Home — Action Centre]] | UX-001 |
| [Action centre — clear](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2898) | [[design/screens/Admin Home — Action Centre]] | UX-001 |
| [Action centre — loading](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-2949) | [[design/screens/Admin Home — Action Centre]] | UX-001 |
| [Network](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3002) | [[design/screens/Admin Doctor Onboarding and Journey Setup]] | ADM-001 / DOR-001 |
| [Onboarding](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3075) | [[design/screens/Admin Doctor Onboarding and Journey Setup]] | DOR-001 / AUTH-001 |
| [Onboarding — review](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3122) | [[design/screens/Admin Doctor Onboarding and Journey Setup]] | DOR-001 |
| [Onboarding — conflict](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3190) | [[design/screens/Admin Doctor Onboarding and Journey Setup]] | AUTH-001 |
| [Commerce](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3227) | [[design/screens/Admin Home — Action Centre]] | ORD-001 / ORD-002 / ORD-004 |
| [Cancellation review](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3310) | [[design/screens/After-sales Request]] | ORD-004 |
| [Cancellation — from message](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4546) | [[design/screens/After-sales Request]] | ORD-004 |
| [Return review](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4602) | [[design/screens/After-sales Request]] | ORD-004 |
| [Record refund](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=61-4658) | [[design/screens/After-sales Request]] | ORD-004 |
| [Content studio](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3366) | [[design/screens/Admin Content Studio]] | CMS-001 |
| [Product workspace](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3439) | [[design/screens/Admin Product Workspace]] | CMS-001 / PRD-001 |
| [Consultation routing](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3497) | [[design/screens/Admin Home — Action Centre]] | CON-001 |
| [More](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3543) | [[design/screens/Admin Home — Action Centre]] | SUP-001 |
| [Access denied](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=50-3626) | [[design/screens/Admin Home — Action Centre]] | AUTH-001 |
| [Payment not verified](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=58-4095) | [[design/screens/Payment Checkout]] | PAY-001 |

## Foundation — DS-CORE (`08`)

Shared chrome module. Role screens instance these; they do not copy them. Masters sit in section `DS-CORE — Components` on this page.

| Frame | Spec | Requirement |
|---|---|---|
| [Overview](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-4) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Tokens](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-28) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Type and targets](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-4651) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Buttons](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-4668) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Fields](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-4687) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Icons and nav](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-4717) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Content](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-4933) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Shell — root](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-5019) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Shell — focused](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-5080) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |
| [Product card](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-5102) | [[design/screens/DS-CORE Shared UI]] | DS-CORE |

## Foundation — Payment (`07`)

Hosted checkout after Review order. Card/UPI details stay on the provider. Paid is a verified callback, not a closed webview.

| Frame | Spec | Requirement |
|---|---|---|
| [Pay](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1003) | [[design/screens/Payment Checkout]] | PAY-001 |
| [Pay — no method](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1071) | [[design/screens/Payment Checkout]] | PAY-001 |
| [Opening payment](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1130) | [[design/screens/Payment Checkout]] | PAY-001 |
| [Confirming payment](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-1166) | [[design/screens/Payment Checkout]] | PAY-001 |
| [Confirming — still pending](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=58-488) | [[design/screens/Payment Checkout]] | PAY-001 |
| [Payment confirmed](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-3841) | [[design/screens/Payment Checkout]] | ORD-003 |
| [Payment failed](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-3902) | [[design/screens/Payment Checkout]] | ORD-003 |
| [Payment cancelled](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-3939) | [[design/screens/Payment Checkout]] | PAY-001 |
| [Payment expired](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=57-3976) | [[design/screens/Payment Checkout]] | ORD-003 |
| [Pay later](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=58-358) | [[design/screens/Payment Checkout]] | PAY-001 |
| [Order — awaiting payment](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=58-426) | [[design/screens/Payment Checkout]] | ORD-003 |

## Foundation — Sign in (`06`)

Shared by every role. Guest shop, checkout, doctor/MR/admin homes and Profile/More `Sign out` all enter this sequence.

| Frame | Spec | Requirement |
|---|---|---|
| [Sign in](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-4) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Sign in — invalid](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-43) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Enter OTP](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-77) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Enter OTP — error](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-109) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Enter OTP — expired](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3423) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Enter OTP — verifying](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3453) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Choose workspace](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3483) | [[design/screens/Auth Sign in and Sign out]] | UX-001 |
| [First login — doctor](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3529) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [First login — customer](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3564) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Sign out](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3599) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Signed out](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3637) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |
| [Cannot sign in](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=55-3664) | [[design/screens/Auth Sign in and Sign out]] | AUTH-001 |

## Still later

- Tablet/desktop shells
- Visual photography and final claims copy
- Presentation / deck (tablet-first; deferred)

## Known deliberate omissions

- Doctor-response and feedback outcome values not invented (OQ-001, D-08).
- Offline capture is shown as blocked, not as a working queue (D-10).
- No card/UPI fields in the Srasveda app. Hosted provider page is out of this file. Paid waits for a verified callback (PAY-001).
- After-sales is request-only in the app. Admin accepts or rejects. Refund is recorded after ops pays it — no automatic gateway reverse (ORD-004).
- Consultation shows one assigned partner or a no-match path, never a clinic list.
- Admin product workspace is an overview plus review gate, not all CMS tabs on one phone screen.
- No production implementation is authorised by these frames alone.
