---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User turns on the Credit card toggle on Home before any cutoff day is set"
    kind: actor
    actor: user
    entities:
      - { entity: credit-card, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
  - text: "The User enters the cutoff day and confirms"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product saves the Credit card cutoff day and keeps the toggle on"
    kind: product
    actor: user
    entities:
      - { entity: credit-card, effect: changes, facts: [Cutoff day] }
    contexts:
      app:
        place: android-app::home
---

# Set the cutoff day on the first credit expense

## Trigger

The first expense paid with the credit card is being entered.

## Outcome

The cutoff day is set and the expense can be recorded as a credit card expense.
