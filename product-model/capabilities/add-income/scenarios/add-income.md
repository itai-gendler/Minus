---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User types + and an amount on the numpad"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The budget pill shows that the amount will be added"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The User taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the Expense as Income added in the active Budget period"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
---

# Add income to the budget

## Trigger

The User receives money they want to spend in this period.

## Outcome

The amount is recorded as Income added and raises what is left in the period.
