---
id: ENG-001
title: Feature harness and scenario testing
status: draft
owner: engineering-product
priority: foundation
---

# ENG-001 — Feature Harness and Scenario Testing

## User outcome

Every feature can be changed, tested and released without accidentally breaking another role or business journey. Before a feature is considered complete, its expected behaviour, permissions, data, integrations and failure modes are executable—not merely described in a document.

## Architecture rule: isolated vertical slices

Use one deployed Next.js application and one controlled database at first—a **modular monolith**, not many separately deployed services. Each feature remains isolated in its own folder/package boundary.

```text
src/features/<feature>/
  domain/          business rules and types
  application/     commands, queries and use cases
  infrastructure/  database/provider adapters
  ui/              role-specific screens/components
  contracts/       public feature API/events only
  harness/         fixtures, unit/integration/permission tests
  README.md        scope, linked vault requirement and ownership
```

Examples: `orders`, `doctor-journey`, `consultation-routing`, `support`, `content`, `identity` and `whatsapp`.

## Boundary rules

- A feature may use another feature only through its documented contracts/events—not by reaching directly into its private database/repository/UI internals.
- Each feature owns its writes and business invariants. Cross-feature effects use explicit commands/events, for example `order.delivered` or `sample.issued`.
- Shared utilities are small and neutral: authentication primitives, audit logging, provider interfaces, design tokens and test helpers. Do not create a catch-all `utils` business layer.
- Do not split into microservices initially. A new service is considered only when operational scale, security isolation or independent deployment genuinely requires it.

## Required feature harness

Every feature must contain or link to:

| Harness element | Purpose |
| --- | --- |
| Requirement and acceptance criteria | Defines “done”; links to vault ID |
| Permission matrix | States exactly which role may read/create/update/approve each action |
| Fixture builder | Creates isolated realistic data for that feature |
| Unit tests | Business rules, transitions and calculations |
| Integration tests | Database, API/server action and feature-contract behaviour |
| Permission tests | Proves blocked cross-role/cross-record access |
| End-to-end path | Exercises the user-visible happy path and key failure paths |
| Provider simulator | Replays payment, WhatsApp and delivery webhooks without live external traffic |
| Observability checks | Audit event, structured log/metric and error handling expectations |
| Release checklist | Migration, rollback, feature flag and support/runbook notes |

## Definition of done

A feature cannot be marked `verified` or released until its harness passes in a production-like test environment, its linked acceptance criteria are checked, and any external-provider behaviour has been simulated including duplicate/failure callbacks.

## Test-environment safety

- Use a separate test database/storage bucket and resettable seeded fixtures for every run.
- Use test-only OTP/session helpers; never add an OTP bypass that can operate in production.
- Payment, WhatsApp and delivery providers are represented by interfaces/adapters. Tests use deterministic simulators; later, approved sandbox tests verify the real providers.
- No real customer/doctor phone number, personal data, payment or WhatsApp message is used in automated tests.

## Linked records

- [[tests/SCN-001 Full Business Simulation]]
- [[tests/MR-001 Complete Doctor Visit Test]]
