---
type: screen-spec
id: UI-ADM-003
status: draft
roles: [admin, content-editor, compliance-reviewer]
---

# UI-ADM-003 — Admin Content Studio

```text
Content Studio
Tabs: Products | Media library | Pages & banners | Brand settings | Social | Review queue | History

Product: [Product name]
  Images: [primary image] [gallery] [+ Upload]
  Approved copy fields / decks / audience visibility
  Used on: Product page, MR presentation, doctor resource page
  [Open Product Workspace] [Save draft] [Preview] [Submit for review]

Publication panel
  Version, change summary, reviewer, approval state, scheduled/live time
  [Approve] [Publish] [Unpublish] [Rollback]
```

## Key behaviour

- A photo upload is not live until published by the permitted role.
- Image replacement shows a before/after preview and all places where it is used.
- Brand settings are restricted fields, never an arbitrary page builder or code editor.
- Public/professional/internal audience preview prevents showing the wrong deck or content to the wrong role.
- Social lets the editor choose approved assets, make channel-specific copy, submit it for approval and either record a manual post URL or use a later authorised connection.
- Social has two content choices: `Official Ayurveda update` (requires source URL/date/attribution) and `Srasveda activity` (requires event facts and permissions). Both use the same approval/publish history.
