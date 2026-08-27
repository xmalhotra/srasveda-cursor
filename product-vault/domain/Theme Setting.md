---
type: domain-object
status: draft
---

# Theme Setting

A constrained brand setting an admin can safely update without breaking the application design. Values bind to [[requirements/DS-CORE Shared UI System]] token slots.

## Editable

- Logo/favicons, named brand colours, homepage hero/banner, approved font choice and footer/contact details.

## Not dashboard-editable

- Arbitrary CSS/JavaScript, layout logic, checkout/payment behaviour, permissions or security settings.
- New page/component types; these require a [[requirements/DS-CORE Shared UI System]] change and code deployment.

## Rules

- Every change has preview, approval/publish action, audit history and rollback.
- Invalid contrast, asset size or required fields block publication.
