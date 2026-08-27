---
type: screen-spec
id: UI-MR-002
status: draft
roles: [mr]
figma: https://www.figma.com/design/YITNo7Xfit8BR5FIa3hPcF?node-id=17-37
---

# UI-MR-002 — My doctors

## Job to be done

The assigned MR sees only their doctors, each with relationship stage, last interaction and the next required action, then opens a doctor record without browsing a global directory.

## Page structure

```text
Header: Srasveda | Support · MR name
Title: My doctors
Search: assigned doctors or clinic

LIST (assigned only)
  Doctor name · primary clinic
  Stage · last interaction · next action
  [ Open doctor ]

BOTTOM NAVIGATION
  Today | Doctors (active) | Tasks | Activity | More
```

## Behaviour

- Search filters the assigned list only.
- `Open doctor` goes to [[design/screens/MR Doctor Detail]].
- Empty assigned list: “No doctors assigned — request onboarding.”

## Must not show

Unassigned doctors, other MR territories, internal price rules, patient data.

## Figma

Drawn on `01 Journeys — Customer MR Doctor` as `UI-MR-002 My doctors`.

## Links

- [[requirements/MR-001 Complete Doctor Visit]]
- Registry ID MR-002 (directory / assignment visibility — still discovery)
