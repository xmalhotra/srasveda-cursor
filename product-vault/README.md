# Srasveda Product Vault

This is the canonical, editable source of truth for the Srasveda digital platform.

Open this folder as an Obsidian vault if you want graph view and clickable `[[links]]`. Keep it in the project repository so every decision, design, test and code change can be traced.

## Build lock

No production-feature implementation begins until [[Build Readiness Checklist]] is completed and the founder explicitly approves the build scope. This vault remains the source of truth for pre-build discovery, requirements, design, evidence and test-harness work.

## Operating rule

No feature is built from a chat message or a vague screen request. It must have:

1. a feature contract in `requirements/`;
2. linked workflow, domain and permission rules;
3. acceptance scenarios in `tests/`;
4. an approved visual screen reference in `design/` before UI development;
5. an explicit status of `approved` before work starts.

## Status vocabulary

| Status | Meaning |
|---|---|
| `discovery` | Evidence is being collected; no behaviour is assumed. |
| `draft` | A proposed contract exists; review is needed. |
| `review` | Ready for a founder/MR/design review. |
| `approved` | Scope is locked for the stated release. |
| `building` | Approved work is being implemented. |
| `verified` | Acceptance scenarios passed. |
| `released` | Available to users. |
| `deprecated` | Retired, with a successor or reason recorded. |

## Navigation

- [[Home]] — visual entry point and product map.
- [[registry]] — every requirement and its current status.
- [[workflows/WF-MR-001 Clinic Visit]] — first workflow being specified.
- [[requirements/MR-001 Complete Doctor Visit]] — first feature contract.
- [[decisions/ADR-001 Version One Boundary]] — confirmed scope boundary.
- [[design/README]] — UI and design-system handoff rules.
- [[tests/README]] — acceptance-test rules.

## Editing rules

- Add an open question rather than inventing an answer.
- Mark assumptions with `ASSUMPTION` and link the evidence when confirmed.
- Do not silently change an approved requirement; add a dated change entry and return it to `review`.
- Do not duplicate a concept. Link to its existing domain page instead.
