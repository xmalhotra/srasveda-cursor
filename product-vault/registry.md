---
type: requirement-registry
---

# Requirement Registry

| ID | Requirement | Status | Release | Workflow | Screen | Tests |
|---|---|---|---|---|---|---|
| MR-001 | [[requirements/MR-001 Complete Doctor Visit]] | draft | Phase 1 | [[workflows/WF-MR-001 Clinic Visit]] | [[design/screens/MR Log Visit]] | [[tests/MR-001 Complete Doctor Visit Test]] |
| MR-002 | Doctor directory and dedicated MR assignment visibility | discovery | Phase 1 | Pending | [[design/screens/MR My Doctors]] | Pending |
| MR-003 | Product presentation mode | discovery | Phase 1 | Pending | Pending | Pending |
| PRD-001 | [[requirements/PRD-001 Product Deck and Product Page]] | draft | Phase 1 | Pending | Pending | Pending |
| PRD-002 | [[requirements/PRD-002 Doctor Product Relationship]] | draft | Phase 1 | Pending | Pending | Pending |
| PRD-003 | [[requirements/PRD-003 Next Sample Queue]] | draft | Phase 1 | Pending | Pending | Pending |
| ADM-001 | Admin doctor/MR assignment | discovery | Phase 4 | Pending | [[design/screens/Admin Doctor Onboarding and Journey Setup]] | Pending |
| DOC-001 | Doctor professional resource access | discovery | Phase 2 | Pending | [[design/screens/Doctor Home — Professional Resources]] | Pending |
| ORD-001 | [[requirements/ORD-001 Doctor Attributed Customer Order]] | draft | Phase 3 | [[workflows/WF-ORD-001 Doctor Attributed Customer Order]] | [[design/screens/Customer Home — Shop and Orders]] | Pending |
| ORD-002 | [[requirements/ORD-002 Doctor Clinic Reorder]] | draft | Phase 2 | [[workflows/WF-ORD-002 Doctor Clinic Reorder]] | [[design/screens/Doctor Order Detail — Receipt and Delivery]] | Pending |
| ORD-003 | [[requirements/ORD-003 Customer Order Lifecycle and WhatsApp Status]] | draft | Phase 3 | [[workflows/WF-ORD-003 Customer Order Lifecycle]] | [[design/screens/Customer Home — Shop and Orders]] | Pending |
| ORD-004 | [[requirements/ORD-004 Manual After-sales]] | draft | with-ordering | [[workflows/WF-ORD-004 Manual After-sales]] | [[design/screens/After-sales Request]] | Pending |
| DISC-001 | Doctor/customer discount code | discovery | build phase pending | Pending | Pending | Pending |
| COM-001 | [[requirements/COM-001 WhatsApp Updates]] | draft | phase-1 foundation | [[workflows/WF-COM-001 WhatsApp Updates]] | Pending | Pending |
| PAY-CORE | [[requirements/PAY-CORE Hosted Payment Adapter]] | draft | with-ordering | Pending | [[design/screens/Payment Checkout]] | Pending |
| PAY-001 | [[requirements/PAY-001 Verified Online Payment]] | draft | with-ordering | [[workflows/WF-ORD-003 Customer Order Lifecycle]] | [[design/screens/Payment Checkout]] | Pending |
| CON-001 | [[requirements/CON-001 Consultation Request and Private Partner Routing]] | draft | Phase 3 | [[workflows/WF-CON-001 Consultation Routing]] | [[design/screens/Customer Home — Shop and Orders]] | Pending |
| UX-001 | [[requirements/UX-001 Role-based Application Experience]] | draft | Phase 1 | [[design/Role-based Experience Map]] | [[design/Figma Wireframe Inventory]] | Pending |
| SUP-001 | [[requirements/SUP-001 Role-aware Support and Internal Tickets]] | draft | Phase 1 | [[workflows/WF-SUP-001 Support Request]] | Pending | Pending |
| PUB-001 | [[requirements/PUB-001 Heritage and Trust Experience]] | draft | Phase 1 | [[design/Heritage and Trust Experience]] | Pending | Pending |
| AUTH-CORE | [[requirements/AUTH-CORE Phone OTP Session]] | draft | Foundation | Pending | [[design/screens/Auth Sign in and Sign out]] | Pending |
| AUTH-001 | [[requirements/AUTH-001 Account Provisioning and Role Activation]] | draft | Foundation | [[workflows/WF-AUTH-001 Account Provisioning and Role Activation]] | [[design/screens/Auth Sign in and Sign out]] | Pending |
| DOR-001 | [[requirements/DOR-001 Doctor Onboarding and Relationship Playbook]] | draft | Phase 1 | [[workflows/WF-DOR-001 Doctor Relationship Lifecycle]] | [[design/screens/Admin Doctor Onboarding and Journey Setup]] | Pending |
| CMS-001 | [[requirements/CMS-001 Content, Media and Theme Management]] | draft | Phase 4 | [[workflows/WF-CMS-001 Publish Content Change]] | [[design/screens/Admin Content Studio]] | Pending |
| SOC-001 | [[requirements/SOC-001 Social Presence and Publishing]] | draft | Phase 1 links; automation later | [[workflows/WF-SOC-001 Social Content Publication]] | Pending | Pending |
| REV-001 | [[requirements/REV-001 Reviews and Credibility Evidence]] | draft | Phase 1 | [[workflows/WF-REV-001 Review and Story Publication]] | Pending | Pending |
| VID-001 | [[requirements/VID-001 Doctor Video Perspectives]] | draft | before public doctor video | Pending | Pending | Pending |
| ENG-001 | [[requirements/ENG-001 Feature Harness and Scenario Testing]] | draft | Foundation | [[tests/SCN-001 Full Business Simulation]] | Pending | Pending |
| DS-CORE | [[requirements/DS-CORE Shared UI System]] | draft | Foundation | Pending | [[design/screens/DS-CORE Shared UI]] | Pending |

## How to add a feature

1. Copy [[requirements/Feature Template]].
2. Allocate a permanent ID by area: `MR`, `ADM`, `DOC`, `ORD`, `PAY`, `PUB`, `AUTH`, `DS`, or `*-CORE` for reusable modules.
3. Add a row here.
4. Link a workflow, domain objects, screen specification and tests.
5. Keep status `discovery` until evidence exists; do not promote directly to `approved`.
