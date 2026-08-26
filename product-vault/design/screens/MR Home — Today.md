---
type: screen-spec
id: UI-MR-001
status: draft
roles: [mr]
---

# UI-MR-001 — MR Home: Today

## Job to be done

Within a few seconds, an MR knows who to meet, what is overdue, which doctor needs the next action and can start a visit without hunting through records.

## Page structure

```text
Header: Srasveda | Today, 8 Aug | Support | Notifications | Profile

Greeting: Good morning, [MR name]
Primary action: + Start visit

TODAY'S PRIORITIES
  1. 10:30 — Dr [Name], [Clinic]          [Start visit]
     Follow up on [Product] sample • Due today
  2. Dr [Name], [Clinic]                  [Open task]
     First-sale review • Due today
  3. Dr [Name], [Clinic]                  [Plan visit]
     Product introduction overdue 2 days

MY DAY
  Planned visits (n) | Open tasks (n) | Overdue (n)
  Compact, ordered activity list with time/area where available

QUICK ACCESS
  My doctors | Tasks | Presentation mode | Add doctor / request onboarding

BOTTOM NAVIGATION
  Today | Doctors | Tasks | Activity | More
```

## Information priority

1. Overdue or due-today business actions.
2. Next planned visit and a single-tap `Start visit` action.
3. Tasks created from sample feedback and sales checkpoints.
4. Personal daily activity—not a distracting leaderboard.

## Behaviour

- The list defaults to today; overdue tasks appear first with a clear reason and due date.
- `Start visit` opens the doctor selector if no visit was pre-planned, then opens visit mode.
- `Open task` shows exact required evidence, not merely “complete task”.
- `Presentation mode` opens only approved product decks and is tablet-friendly.
- `Support` creates an internal support ticket then opens the approved admin/operations contact route.
- Empty state: “No actions due today” plus planned future visit/task and `My doctors` action.
- Offline behaviour is a later requirement; until approved, the screen must clearly show when it cannot save a visit.

## Data shown

- Assigned doctor's name, primary clinic, area, relationship stage and next action.
- Task type, due date, source (sample/feedback/sales/onboarding), priority and completion state.
- Planned visit time/area when supplied.

## Must not show

- Other MR territories, global doctor list, private referral routing, price control, other MR performance, patient/medical data or unapproved claims.

## States to design later

- New MR with no assigned doctors.
- Task due today; overdue task; all work complete.
- Doctor reassigned while an old task remains in history.
- No internet / save pending, if offline entry is approved.

## Links

- [[requirements/DOR-001 Doctor Onboarding and Relationship Playbook]]
- [[domain/Automated MR Task]]
- [[requirements/MR-001 Complete Doctor Visit]]
