---
type: domain-object
status: draft
---

# Theme Setting

A constrained brand setting an admin can safely update without breaking the application design.

## Editable

- Logo/favicons, named brand colours, homepage hero/banner, approved font choice and footer/contact details.

## Not dashboard-editable

- Arbitrary CSS/JavaScript, layout logic, checkout/payment behaviour, permissions or security settings.
- New page/component types; these require design and code deployment.

## Rules

- Every change has preview, approval/publish action, audit history and rollback.
- Invalid contrast, asset size or required fields block publication.
