---
id: TEST-MR-001
requirement: [[requirements/MR-001 Complete Doctor Visit]]
status: draft
---

# TEST-MR-001 Complete Doctor Visit

## Access control

```gherkin
Given MR A is not assigned to Doctor B
When MR A attempts to start or submit a visit for Doctor B
Then the system denies access
And no visit, sample or follow-up record is created
```

## Required next action

```gherkin
Given an assigned MR has selected a doctor and products discussed
When the MR tries to complete a visit without a next action and due date
Then the system explains the missing fields
And the visit is not completed
```

## Successful sample visit

```gherkin
Given an assigned MR has completed valid visit details and one valid sample item
When the MR completes the visit
Then the visit appears in the doctor timeline
And the sample is linked to that visit and doctor
And a follow-up is created for the assigned MR
And the doctor next-action summary is updated
```

## Invalid sample quantity

```gherkin
Given an assigned MR adds a sample item with zero or negative quantity
When the MR attempts to complete the visit
Then the system rejects the quantity
And creates no sample record
```

## Audit trail

```gherkin
Given an Admin corrects an existing completed visit under the approved correction process
When the change is saved
Then an audit event records who changed what, when and why
```
