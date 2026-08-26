---
type: domain-object
status: draft
access: admin-only
---

# Journey Configuration Option

The controlled reference data behind admin dropdowns in doctor onboarding/journey setup.

## Option sets

- Active product — derived from approved active [[domain/Product]] records.
- Sample quantity — allowed values maintained by admin (for example pack/units as approved for that SKU).
- Feedback outcome — approved, factual outcomes such as recorded feedback, needs further follow-up, no response, not interested, or another defined business outcome.
- Doctor tier, sales-checkpoint plan, communication language and relationship stage where configured.

## Rules

- Options have active/inactive status, effective date, owner and audit history.
- A journey uses a product dropdown and quantity dropdown; quantity options may be limited by selected product.
- Admin may add/remove future options, but cannot silently change an option already used in historical onboarding/sample records.
- The definitive feedback-outcome list needs founder/operations approval before build.
