---
type: domain-object
status: draft
related: [[domain/Doctor]], [[domain/Doctor Clinic Affiliation]]
---

# Clinic / Hospital

A healthcare organisation or practice location associated with one or more doctors.

## Minimum attributes

- legal/display name;
- type: clinic, hospital, ayurvedic clinic, other approved type;
- address, city, area and contact details as operationally required;
- active/inactive status.

## Rule

The clinic/hospital is a separate record from the doctor. A doctor moving to a new clinic creates/ends an affiliation; it does not overwrite historical visit or order context.
