---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User taps UNDO on the deletion snackbar"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the Expense again"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
---

# Undo a deletion

## Trigger

The User deleted an expense and changes their mind within a few seconds.

## Outcome

The expense is back with its values and the budget is recalculated.

## Edge cases

- After the snackbar disappears, about three and a half seconds later, the deletion can no longer be undone.
- If it cannot be restored, Could not restore transaction is shown.
