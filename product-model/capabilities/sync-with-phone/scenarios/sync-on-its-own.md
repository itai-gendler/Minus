---
kind: alternative
routes:
  watch: Wear OS watch
steps:
  - text: "An Expense waits on the watch and the watch's regular sync comes due"
    kind: condition
    unattended: true
    entities:
      - { entity: expense, effect: reads, facts: [] }
    contexts:
      watch:
        place: wear-app::period-overview
  - text: "The Product sends the Expense to the phone, which records it in its active Budget period"
    kind: product
    entities:
      - { entity: expense, effect: changes, from: "Waiting for phone", to: "Recorded", facts: [] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      watch:
        place: wear-app::period-overview
---

# Sync on its own

## Trigger

Fifteen minutes have passed, or the watch app opened, since an expense was saved.

## Outcome

The expense is recorded on the phone without the User doing anything.
