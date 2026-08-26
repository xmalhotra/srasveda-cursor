---
type: delivery-readiness
status: active
---

# Build Readiness Checklist

The vault now covers the major business journeys. This checklist separates that coverage from actual build readiness. A section moves to complete only after its linked decisions, designs and acceptance tests are approved.

Decision proposals are collected in [[Founder Decision Workbook]]. A proposal is not an approved policy until the named business owner confirms it.

## 1. Business decisions still needed — blocker

- [~] Doctor onboarding is manual admin action; sampling uses product/quantity dropdowns; feedback is due at 7 days and 1 month with outcome. Still define outcome list and sales-checkpoint thresholds. See [[requirements/DOR-001 Doctor Onboarding and Relationship Playbook]].
- [~] Customer orders are direct; doctor/clinic orders are restock supply; internal delivery uploads delivery proof. Still define delivery fields, attribution, discount, tax, cancellation and return rules. See [[requirements/ORD-001 Doctor Attributed Customer Order]] and [[requirements/ORD-003 Customer Order Lifecycle and WhatsApp Status]].
- [~] Doctor/clinic regular order means stock-restock supply; internal delivery fulfils it. Still define price/discount, tax and returns. See [[requirements/ORD-002 Doctor Clinic Reorder]].
- [~] Consultation requests map to an area; a default partner or authorised manual assignment is selected in dashboard. Still define exact mapping, eligibility, customer lead-sharing consent and no-match handling. See [[requirements/CON-001 Consultation Request and Private Partner Routing]].
- [~] MSG91 and number `9255427911` selected for pre-structured messages. Still confirm Meta/MSG91 onboarding, display name, language, template owner and trigger policy. See [[requirements/COM-001 WhatsApp Updates]].
- [~] Founding/GST/founder/sales evidence is available; still upload/verify it and obtain/publicly scope hospital/clinic and testimonial permissions. See [[requirements/PUB-001 Heritage and Trust Experience]].

## 2. Product and compliance content — blocker for public launch

- [~] Existing source contains 23 product records, images, ingredients, usage, FAQs and public copy. Still create verified SKU records with classification, pack/variant, price, warnings, storage, manufacturer/licence evidence, approval and claim review. See [[discovery/Existing Product Content Audit]].
- [ ] Name the content/regulatory approver and publish/review cadence. See [[discovery/Existing Product Content Audit]].
- [~] Existing product descriptions/benefits include condition/outcome statements that need SKU/category-specific review before reuse. Public deck/template approval remains pending. See [[discovery/Existing Product Content Audit]].
- [~] Existing Privacy and Terms pages provide a start. Still replace generic/WhatsApp-order wording with direct-checkout, consent, internal-delivery and consultation-routing terms. Use competitor policy structure as a reference, not copied text. See [[discovery/Existing Product Content Audit]].

## 3. Screen design still required — blocker for the relevant feature

### First screens completed in draft

- [x] Customer home
- [x] Doctor home
- [x] MR home
- [x] Admin action centre

### Detailed screens still to design

- [ ] Product listing, product detail and product-resource/deck views.
- [ ] Cart, checkout, payment result, order history and order-status timeline.
- [ ] Customer consultation request and selected-partner contact state.
- [ ] MR doctor detail, visit mode, sample capture, feedback capture and task completion/exception states.
- [ ] Doctor onboarding/assignment and playbook configuration.
- [ ] Admin: orders/fulfilment, product/price approval, private partner routing, support worklist and audit-log views.
- [ ] Empty, error, access-denied, OTP/login and mobile/tablet layouts.

## 4. Technical/security specification — blocker before implementation

- [ ] Record the production architecture decision: Next.js deployment, database, file storage, authentication/OTP, payment provider, WhatsApp provider, domain/DNS and backups.
- [ ] Approve pre-provisioned account, self-service signup, role-promotion and duplicate-mobile resolution rules. See [[requirements/AUTH-001 Account Provisioning and Role Activation]].
- [ ] Define roles/permissions in a testable matrix: customer, doctor, MR, distributor/fulfilment, operations, admin and compliance reviewer.
- [ ] Define audit-log retention, privacy/data deletion/retention policy, access-review process and incident/support ownership.
- [ ] Define payment webhook verification, WhatsApp webhook verification, rate limits, anti-abuse controls and monitoring/error alerts.
- [ ] Define data migration/import process for existing doctors, clinics, MR assignments, products, prices and historical orders—plus who verifies it.

## 5. Tests and launch proof — blocker before public release

- [ ] Create acceptance-test files for every requirement, not only MR-001.
- [ ] Implement the feature-harness standard and automated full business simulation using isolated test data/providers. See [[requirements/ENG-001 Feature Harness and Scenario Testing]].
- [ ] Write permission/security tests: especially network confidentiality, partner routing, price integrity and cross-role access.
- [ ] Run real MR/operations user-acceptance tests with sample data and a real clinic-visit simulation.
- [ ] Test payment, fulfilment and WhatsApp notifications in sandbox/test mode, including duplicate callbacks and failures.
- [ ] Prepare operations runbook: who answers support, fulfils orders, handles no-match referrals, corrects errors and pauses a product/partner.
- [ ] Launch first to a limited, monitored group; review support volume, routing results, order exceptions and message delivery before broad promotion.

## Recommended build sequence

1. Foundation: roles/OTP, admin user management, doctor/clinic/MR import, product catalogue and audit log.
2. MR core: doctor detail, visit logging, samples, automated tasks and playbook.
3. Customer commerce: products, price, checkout/payment, order lifecycle and support.
4. WhatsApp operational notifications.
5. Private consultation routing.
6. Doctor portal, distributor workflow, advanced reports and refinement.

## Build lock — founder decision

**No production-feature implementation starts until this readiness checklist is completed and the founder explicitly approves the build scope.**

Permitted before the lock is lifted: discovery, requirements, design/wireframes, evidence collection, data clean-up planning, architecture decisions and test-harness specification.

Not permitted before the lock is lifted: production database schema/migrations, login/OTP, checkout/payment, role portals, admin dashboard, provider integrations or feature code presented as build work.

The next practical milestone is to close the business decisions in section 1, then detailed wireframes, technical/security decisions and acceptance-test plans. After every launch-blocking item is complete, create an explicit founder build-approval record.
