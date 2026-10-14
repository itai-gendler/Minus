---
kind: edge
routes:
  watch: Wear OS watch
steps:
  - text: "The User taps Sync now while the phone is out of reach"
    kind: actor
    actor: user
    entities: []
    contexts:
      watch:
        place: wear-app::period-overview
  - text: "The Product keeps each Expense waiting and tries again later"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [] }
    contexts:
      watch:
        place: wear-app::period-overview
---

# The phone is not reachable

## Trigger

The phone is off, far away or lacks the watch connection.

## Outcome

The expenses stay on the watch and go out on a later sync; the overview keeps the budget last received.
