---
type: domain-object
status: draft
access: admin-only
---

# Referral Routing Policy

The versioned server-side rule that selects one target from the private eligible partner pool.

## Baseline selection

1. Resolve the customer zone.
2. Filter active, referral-eligible partners whose approved zones match.
3. Exclude unavailable/capped partners and those in cooldown.
4. Use an active configured default partner for the mapped zone where one exists, or send to the authorised manual-assignment queue. Any optional future priority/rotation rule applies only after founder approval.
5. Log policy version, internal candidates, selected target and selection reason.

## Guardrails

- Runs only on the server and returns at most one approved customer contact card.
- The admin worklist shows request, mapped zone and eligible/manual-assignment controls; it is never a public directory.
- A no-match result is valid and returns a neutral Srasveda escalation path.
- Policy changes require approval, versioning and audit.
