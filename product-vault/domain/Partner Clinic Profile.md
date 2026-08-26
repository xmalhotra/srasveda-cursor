---
type: domain-object
status: draft
access: admin-only
---

# Partner Clinic Profile

The private, internal record deciding whether a [[domain/Clinic Hospital]] or associated doctor can receive consultation referrals. It is not a public clinic listing.

## Fields

- Linked clinic and optional contact doctor; referral-eligibility and approval owner.
- Covered zones; approved customer contact card; capacity, temporary availability, cap and cooldown.
- Internal priority tier/effective dates; agreement/compliance references; suspension reason and audit history.

## Visibility boundary

- Only authorised admin/operations users may browse this registry.
- There is no public page, public search, map marker, predictable URL or client-side export.
- A customer receives only the selected partner's approved contact card—not candidates, alternatives or network size.

## Rule

Internal priority is a business-routing input, not a claim that a selected clinician is medically superior.
