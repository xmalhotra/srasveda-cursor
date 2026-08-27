---
type: domain-object
status: draft
---

# Support Ticket

An internal management record automatically created when a logged-in user chooses Support. It tracks ownership and closure without becoming a user-facing ticket portal.

## Fields

- Requester role and account; source screen and timestamp.
- Routing target at creation: official Srasveda support, assigned MR, or admin/operations.
- Optional linked order, doctor, clinic, visit or task, only if the user chose the relevant context.
- Internal owner, priority and tags.
- Status: `new`, `assigned`, `in-progress`, `waiting-internally`, `closed`.
- Internal notes, manual close reason, closer and audit timestamps.

## Rules

- Creating the ticket does not disclose its status, internal notes, owner, tags or closure to the requester.
- Only authorised management/support users receive ticket notifications and can view/update/close tickets.
- Tickets are manually closed; a WhatsApp conversation or elapsed time cannot close one automatically.
- A ticket stores only minimum context. It must not collect medical/patient details or copy unrestricted chat content into the platform.
- If no assigned MR exists for a doctor, the ticket routes to management's fallback queue and the contact route follows the approved fallback policy.
- An after-sales request may create or link a ticket for the admin worklist. Ticket status is still not shown to the requester. The customer-safe signal is on the order: request received / decision. See [[domain/After-sales Request]].
