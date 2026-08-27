---
type: screen-spec
id: UI-MR-05
status: draft
roles: [mr]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-128
---

# UI-MR-05 — Log visit

## Job to be done

An assigned MR completes a routine post-visit record in two minutes: what was discussed, optional samples, and a required next action so follow-up cannot be lost.

## Page structure

```text
Header: ‹ Back | Support
Title: Log visit
Context: doctor · clinic · stage · latest next action

Visit date / time          default now; editable; not future unless approved
Products discussed *       at least one active product
Doctor response *          controlled option set — OQ-001 pending
Note                       optional
Next action *              controlled option set — pending
Next action due *          date — rule pending
Samples                    optional  [ Add sample: product + quantity ]

Primary: [ Complete visit ]
```

## States drawn

| State | Figma frame |
|---|---|
| Default | [Log visit](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-128) |
| Validation | [Log visit — error](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-180) |
| Sample | [Add sample](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-226) |
| Feedback | [7-day feedback](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-271) |
| Exception | [Can’t complete](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-313) |
| Access denied | [No access](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-358) |
| Offline | [No connection](https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-392) |

Production frames are 390×844 native-app shells on page `03 MR — Mobile app`. Tablet presentation is deferred.

## Placeholders — do not invent values

- Doctor-response options (OQ-001)
- Next-action types
- Feedback outcome list (D-08)
- Offline save (D-10 / OQ-003)

## Must not show

Patient identifiers, invoices, unapproved product claims, other doctors, doctor-facing internal notes.

## Links

- [[requirements/MR-001 Complete Doctor Visit]]
- [[tests/MR-001 Complete Doctor Visit Test]]
- [[design/screens/MR Doctor Detail]]
