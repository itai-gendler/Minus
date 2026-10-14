---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User turns on the Credit card toggle and types the amount"
    kind: actor
    actor: user
    entities:
      - { entity: credit-card, effect: reads, facts: [] }
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
  - text: "The Product records the Expense as paid with the credit card and adds it to what is owed"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: credit-card, effect: reads, facts: [Total owed] }
    contexts:
      app:
        place: android-app::home
---

# Record a credit card expense

## Trigger

The User paid with the credit card, with Credit card payments turned on and a cutoff day set.

## Outcome

The expense counts against the budget and is added to the credit card's total owed until it is marked as paid.

## Edge cases

- Turning the toggle on before any cutoff day is set first asks for the cutoff day (set-credit-cutoff-day).
