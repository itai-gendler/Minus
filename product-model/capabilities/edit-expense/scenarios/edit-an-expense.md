---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens an Expense in the history"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount, Category, Date] }
    contexts:
      app:
        place: android-app::history
  - text: "The User changes its values and taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::history
  - text: "The Product saves the changed Expense"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: changes, facts: [Amount, Category, Extra note, Date, Paid with credit card] }
    contexts:
      app:
        place: android-app::history
---

# Edit an expense

## Trigger

An expense was recorded with a mistake.

## Outcome

The expense shows its new values and the budget is recalculated; a new category name creates that category.

## Edge cases

- Saving an amount of zero fails with Could not save transaction and the expense keeps its values.
