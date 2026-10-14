---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User swipes an Expense away in the history"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount, Category] }
    contexts:
      app:
        place: android-app::history
  - text: "The Product deletes the Expense and offers UNDO"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: removes, from: "Recorded" }
    contexts:
      app:
        place: android-app::history
---

# Delete an expense

## Trigger

An expense was recorded by mistake.

## Outcome

The expense is gone, the budget is recalculated, and a snackbar names it with UNDO for a few seconds.

## Edge cases

- If the expense cannot be deleted, Could not delete transaction is shown and it stays.
