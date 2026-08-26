---
type: domain-object
status: draft
---

# Delivery Proof

An auditable receipt/proof uploaded by authorised internal delivery staff when an order is handed over.

## Fields

- Linked customer or doctor/clinic order; delivery date/time; delivery staff identity.
- Receipt/proof file, recipient name/acknowledgement where collected and delivery exception/remark.
- Customer-safe version visibility and internal audit version/access rules.

## Rules

- Uploading proof may support a `delivered` order event but cannot overwrite earlier history.
- The delivery agent can upload proof but cannot edit order price, attribution or unrelated records.
- Any sensitive signature/contact detail is access-controlled and not exposed outside the appropriate order/role.

## Visibility

- The dedicated doctor/clinic sees only receipt/proof and customer-safe delivery status for their own order.
- The assigned order handler sees only orders assigned to them and the operational fields required to fulfil/deliver them.
- Admin can view the complete audit/evidence record under authorised permission.
