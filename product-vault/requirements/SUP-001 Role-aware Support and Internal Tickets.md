---
id: SUP-001
title: Role-aware support and internal tickets
status: draft
owner: operations
priority: phase-1
---

# SUP-001 — Role-aware Support and Internal Tickets

## User outcome

Any logged-in user can ask for help through the correct familiar contact route. Management gets an internal, manually closed support record for oversight; the requester does not receive ticket-management notifications or see internal ticket information.

## Routing

| Logged-in role | Contact route after Support click | Internal ticket route |
| --- | --- | --- |
| Customer | Official Srasveda WhatsApp account, with approved prefilled text | Customer support/operations queue |
| Doctor | Currently assigned MR's approved phone/WhatsApp contact | Assigned MR with management visibility |
| MR | Designated admin/operations support contact | Admin/operations queue |
| Admin | Internal support/work queue or configured escalation contact | Authorised management queue |

## Required behaviour

1. User selects `Support`; optionally chooses a supported context such as the current order, doctor, visit or task.
2. Server creates a [[domain/Support Ticket]] and routes it from the current role/assignment rules.
3. The application opens the approved WhatsApp/call contact route with minimal, approved prefilled context.
4. Management/assigned support staff receive the internal alert and use the support worklist to own, note and manually close the ticket.

Order cancel/return is not this Support click. That is an [[domain/After-sales Request]] from the order (`Request cancel or return`) or a message that ops files against the order. Both land in the admin action centre. See [[requirements/ORD-004 Manual After-sales]]. A support ticket may be linked for the worklist; the requester still has no ticket portal.

## Privacy and visibility rules

- No ticket receipt, status change, assignment, reminder, internal note or closure notification is sent to the user through the platform.
- The user cannot view a ticket ID, worklist, status, internal notes or closure reason.
- Prefilled WhatsApp text must be limited to the identity/context necessary to start support; never include medical data, private partner-network data or internal routing details.
- Support ticket permissions follow the minimum necessary rule. A doctor’s ticket is not visible to unrelated MRs; a customer ticket is not visible to unrelated doctors.

## Admin / management worklist

- Filter by status, owner, requester role, route, age and linked context.
- Assign/reassign with audit history; add internal notes; manually close with resolution reason.
- Alert only authorised staff on creation, escalation or assignment.
- Preserve source context while preventing edits to the underlying order/visit record through the ticket alone.

## Acceptance tests

- A customer support click creates a ticket and opens only the official WhatsApp route.
- A doctor support click uses the current assigned MR; without one it creates a fallback management ticket without exposing an internal error.
- An MR support click routes to admin/operations, not to another MR or customer channel.
- A requester receives no platform notification when the ticket is assigned, updated or closed.
- Only authorised staff can see the ticket queue, internal notes or close action.
- Ticket closure requires a human action and a recorded resolution reason.

## Linked records

- [[workflows/WF-SUP-001 Support Request]]
- [[domain/Support Ticket]]
- [[requirements/UX-001 Role-based Application Experience]]
- [[requirements/ORD-004 Manual After-sales]]
