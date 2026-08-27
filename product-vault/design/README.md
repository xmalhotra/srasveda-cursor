# Design System and UI Contract

Figma is the visual source of truth; this folder is the machine-readable and product-readable link between Figma and requirements.

The shared chrome is a platform module: [[requirements/DS-CORE Shared UI System]]. Role screens compose it.

## UI work cannot start from theme alone

Each screen must link to:

- an approved requirement;
- a workflow;
- roles/permissions;
- fields and validation states;
- component rules;
- acceptance tests.

## Required Figma structure

```text
00 Brand direction
01 Foundations (colour, typography, spacing, icons)
02 Components
03 MR mobile
04 MR tablet presentation
05 Admin
06 Public/doctor resources
07 Prototypes
08 Handoff
```

## Required screen states

Every implemented screen is designed for default, loading, empty, validation error, server error, success and permission-denied states where relevant.

## Pending

Srasveda token **values** (cream, forest, sage, Inter, Cormorant wordmark) are locked in the current Figma file. Admin may later override named colours through [[domain/Theme Setting]] / CMS-001. New component types remain a DS-CORE change, not a theme publish.

## Current structural wireframes

The editable application wireframes are tracked in [[Figma Wireframe Inventory]]. Shared chrome is page [`08 DS-CORE — Shared UI`](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=64-2).
