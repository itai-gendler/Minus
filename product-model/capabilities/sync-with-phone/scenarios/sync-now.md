---
kind: primary
routes:
  watch: Wear OS watch
steps:
  - text: "The User taps Sync now on the watch"
    kind: actor
    actor: user
    entities: []
    contexts:
      watch:
        place: wear-app::period-overview
  - text: "The Product sends every Expense waiting on the watch to the phone, which records it in its active Budget period"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: changes, from: "Waiting for phone", to: "Recorded", facts: [] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      watch:
        place: wear-app::period-overview
  - text: "The Product brings the phone's Budget period figures and recent Category names to the watch"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Remaining, Total budget, Spent, Finish date] }
      - { entity: category, effect: reads, facts: [Name] }
    contexts:
      watch:
        place: wear-app::period-overview
---

# Sync now

## Trigger

The User wants the watch and the phone to agree now.

## Outcome

The waiting expenses are recorded on the phone and the watch shows the current budget; Syncing with phone shows while it runs.
