---
type: engineering-standard
status: draft
related: [[requirements/ENG-001 Feature Harness and Scenario Testing]]
---

# Feature Harness Standard

## Example: orders feature

```text
src/features/orders/
  domain/Order.ts
  domain/OrderStatusEvent.ts
  application/placeCustomerOrder.ts
  application/assignOrderHandler.ts
  application/recordDeliveryProof.ts
  infrastructure/orderRepository.ts
  infrastructure/paymentGatewayAdapter.ts
  contracts/orderEvents.ts
  ui/customer/OrderTimeline.tsx
  ui/doctor/OrderReceipt.tsx
  ui/admin/OrderExceptionPanel.tsx
  harness/order.fixture.ts
  harness/order.unit.test.ts
  harness/order.integration.test.ts
  harness/order.permissions.test.ts
  harness/order.e2e.test.ts
  README.md
```

## Feature README template

```text
Purpose:
Vault requirements:
Owned data/invariants:
Public contracts/events:
Roles and permission boundary:
External providers:
Harness commands/tests:
Operational alerts/runbook:
Feature flag / migration / rollback:
```

## Mandatory test categories

1. **Rule:** Is the transition/calculation valid?
2. **Permission:** Can this role do/read it—and can every other role be denied?
3. **Integration:** Does it persist correctly and emit the right explicit event?
4. **Journey:** Can the person complete the real screen flow?
5. **Failure:** What happens on duplicate callback, invalid input, provider failure, cancellation or reassignment?
6. **Audit:** Is the source/action/reason retained for sensitive changes?

## Harness command convention

```text
test:feature:<feature>      unit + integration + permission tests
test:scenario:<scenario>    full seeded cross-feature simulation
test:providers              webhook/provider adapter contract tests
```

Actual command names are chosen when the project is created; the convention ensures they are discoverable and consistent.
