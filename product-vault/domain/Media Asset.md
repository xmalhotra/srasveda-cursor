---
type: domain-object
status: draft
---

# Media Asset

A managed image, PDF, video or other approved file stored outside application code and linked to product/content records.

## Required fields

- Storage key/location, media type, size, dimensions and checksum.
- Title, alt text, intended audience and usage rights/source.
- Linked product/content; display role: primary image, gallery image, deck image or banner.
- Upload owner, approval status, published version and replacement/archive history.

## Rules

- Routine files live in managed object storage/CDN, not website source code.
- Only approved assets can be public. Replacing a primary image publishes a new version and preserves history.
- The system serves an optimised display version; the original is retained under the approved policy.
