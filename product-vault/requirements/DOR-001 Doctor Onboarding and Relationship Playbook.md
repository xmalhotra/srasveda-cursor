---
id: DOR-001
title: Doctor onboarding and relationship playbook
status: draft
owner: sales-operations
priority: phase-1
---

# DOR-001 — Doctor Onboarding and Relationship Playbook

## User outcome

Every doctor entering the network follows a consistent, auditable MR-led journey. The system tells the responsible MR exactly what is next, reminds them when it is due and uses actual feedback/sales checkpoints to propose the next action.

## Required onboarding checklist

Before status becomes `onboarded`, an authorised user must confirm:

- Doctor identity and approved professional contact details.
- Current [[domain/Doctor Clinic Affiliation]] and service zone.
- Primary [[domain/Doctor MR Assignment]].
- Approved relationship status and onboarding owner.
- Applicable playbook version and doctor tier, where used.
- Any approved communication preference before outreach.
- A [[domain/Doctor Journey Assignment]] built from approved configuration options, including sampling and checkpoint rules.

**Confirmed policy:** onboarding is performed manually by an authorised admin. An MR may identify a candidate, but cannot activate a doctor without admin onboarding/approval.

## Admin journey setup at onboarding

The onboarding admin does not type automation rules ad hoc. They select approved values from maintained dropdowns, then may add an audited per-doctor override where authorised.

| Configuration field | Admin selects from | Effect |
| --- | --- | --- |
| Doctor tier / relationship type | Approved tier list | Determines available playbooks and reporting segment |
| Product focus | Approved active SKU list | Limits initial decks, sample proposals and feedback tasks to relevant products |
| Sampling plan | Product dropdown + quantity dropdown | Each configured sample is a product/quantity pair; only active approved products and allowed quantity options appear |
| First follow-up cadence | Approved cadence list | Sets next task due date after introduction/sample | 
| Feedback method / outcome options | Approved response list | Mandatory outcome at the 7-day and 1-month feedback checkpoints; standardises automation branches |
| Sales-checkpoint plan | Approved checkpoint-plan list | Determines first-sale, growth and re-engagement task triggers |
| Communication language / permission | Approved preference values | Selects eligible approved templates only |
| Journey owner | Current primary MR and authorised manager | Sets task ownership/escalation |

### Configuration guardrails

- Dropdown lists are admin-managed reference data with active/inactive status, effective dates and audit history.
- A selection may only reference currently active products, approved sample plans and published playbook/checkpoint versions.
- An admin can create a per-doctor exception only with a reason, approver and expiry/review date. It must not alter the underlying template or other doctors.
- Changing the assignment after onboarding affects future automation only; tasks already created retain the original rules/version.
- The MR can view the assigned journey and its next action, but cannot edit its commercial/sampling rules.
- The initial sample configuration is selected from two controlled dropdowns: **Product** and **Quantity**. Admin may add approved product/quantity rows where the journey needs more than one sample.

## Standard MR journey

| Stage | MR action | Evidence / system result |
| --- | --- | --- |
| Qualification | Verify doctor, clinic, zone and MR ownership | Onboarding checklist completed/approved |
| Product introduction | Present approved product deck for selected SKU | [[domain/Visit]] with product relationship updated |
| Sample proposal | Propose/issue only allowed samples and record quantity | [[domain/Sample]] and feedback due date |
| Feedback | Record factual business/product feedback | [[domain/Product Feedback]] and next task |
| First sale review | Check qualifying attributed customer/clinic order | [[domain/Sales Checkpoint]] creates task |
| Regular relationship | Complete recurring review or re-engagement activity | Outcome updates relationship stage |

## Automation rules

- A published playbook creates the next [[domain/Automated MR Task]] when its trigger occurs: onboarding approved, visit logged, sample issued, feedback due/recorded, or qualifying sales checkpoint reached.
- When a sample is issued, the system creates two separate feedback tasks: **7 days** and **1 month** after issue. Completing either requires an approved feedback outcome; `no response` is an outcome, not a silent completion.
- Tasks are created for the doctor’s current assigned MR; manager/admin may reassign with an audited reason.
- Due dates, reminders and escalation come from the playbook version—not a developer’s hidden assumptions.
- Sales-triggered tasks use confirmed orders and declared attribution rules only.
- The automation never sends free-form WhatsApp, issues a sample, records feedback or marks a doctor active without a human-recorded event.

## Non-goals

- Patient data, medical advice, prescription tracking or clinical outcome scoring.
- An opaque “doctor score” that decides treatment, referral or medical quality.

## Acceptance tests

- A doctor cannot become active/onboarded until required checklist items and MR assignment are complete.
- A recorded sample creates one feedback task with due date according to the assigned playbook.
- A completed feedback record advances the correct product relationship and creates only the next configured task.
- A qualifying confirmed order triggers the matching sales checkpoint once, with source order evidence.
- Changing a playbook does not rewrite previously created tasks or their due-date logic.
- An MR cannot complete/waive another MR’s task without an approved permission and an audit entry.

## Linked records

- [[workflows/WF-DOR-001 Doctor Relationship Lifecycle]]
- [[domain/Doctor Relationship Playbook]]
- [[domain/Automated MR Task]]
- [[domain/Sales Checkpoint]]
- [[domain/Doctor Product Relationship]]
- [[domain/Doctor Journey Assignment]]
- [[design/screens/Admin Doctor Onboarding and Journey Setup]]
