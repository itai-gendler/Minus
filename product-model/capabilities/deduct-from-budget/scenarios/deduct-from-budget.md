---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User types - and an amount on the numpad"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The budget pill shows that the amount will be subtracted"
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
  - text: "The Product records the Expense as Deducted budget in the active Budget period"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
---

# Deduct an amount from the budget

## Trigger

The User wants to take money out of the period's budget.

## Outcome

The amount is recorded as Deducted budget and lowers what is left without appearing as spending.
