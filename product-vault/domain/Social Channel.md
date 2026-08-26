---
type: domain-object
status: draft
---

# Social Channel

An approved official Srasveda social presence, initially Instagram and X, managed centrally rather than through hard-coded website links.

## Fields

- Platform, official profile URL/handle, public display name and active status.
- Purpose: brand, support, professional education or campaign.
- Linked public website placement and UTM/share parameters.
- Optional API connection state, permitted scopes, credential owner and last connection check.

## Rules

- Only approved official profile links appear on the public site.
- API tokens/credentials are encrypted server-side and never visible in the browser or ordinary admin screens.
- Disconnecting a channel stops automation but must not delete prior content/audit history.
