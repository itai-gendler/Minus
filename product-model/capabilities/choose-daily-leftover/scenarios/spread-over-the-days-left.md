---
kind: primary
routes:
  app: Android app
steps:
  - text: "Yesterday's budget was not all spent and Daily amount is Your call each day"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Daily amount, Remaining] }
    contexts:
      app:
        place: android-app::home
  - text: "The User chooses Spread over the days left"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the choice for today and raises the daily amount for the rest of the Budget period"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: changes, facts: [Leftover choices] }
    contexts:
      app:
        place: android-app::home
---

# Spread yesterday's leftover over the days left

## Trigger

A new day starts with unused budget from yesterday.

## Outcome

Every remaining day gets a share of the leftover.
