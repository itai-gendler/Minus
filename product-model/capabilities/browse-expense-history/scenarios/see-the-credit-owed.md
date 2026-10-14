---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User opens the history after paying with the card"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::history
  - text: "The User reads the Credit card total owed and the debt-adjusted balance"
    kind: actor
    actor: user
    entities:
      - { entity: credit-card, effect: reads, facts: [Total owed] }
      - { entity: budget-period, effect: reads, facts: [Remaining] }
    contexts:
      app:
        place: android-app::history
---

# See the credit owed

## Trigger

The User paid some expenses with the credit card.

## Outcome

The total owed and what is left minus that debt are shown.
