# Design System and UI Contract

Figma is the visual source of truth; this folder is the machine-readable and product-readable link between Figma and requirements.

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

The Srasveda visual direction and design tokens are intentionally not chosen yet. They require review of current logo, packaging, product photography and approved content.

## Current structural wireframes

The editable first-pass application wireframes are tracked in [[Figma Wireframe Inventory]]. The Figma Starter plan limits the file to three pages, so it groups the planned areas without changing the required future handoff structure above.
