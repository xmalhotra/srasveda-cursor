---
type: domain-object
status: draft
---

# Content Publication

The versioned, auditable publication state for a product page, deck, homepage banner, heritage page or controlled theme setting.

## Lifecycle

`draft → in-review → approved → published → superseded / archived`

## Rules

- Publishing revalidates affected pages/media cache; it does not require a full application rebuild/deployment.
- An authorised user can roll back to a prior approved version.
- Product claims, regulatory facts, doctor quotes and public reviews follow their linked stricter approval rules.
- Urgent unpublish is available to authorised admin/compliance users and is audited.
