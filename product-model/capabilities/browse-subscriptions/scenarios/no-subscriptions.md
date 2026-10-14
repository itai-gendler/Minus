---
kind: edge
routes:
  app: Android app
steps:
  - text: "The User opens Subscriptions"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::subscriptions
  - text: "No Recurring expense is active"
    kind: condition
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::subscriptions
---

# No subscriptions yet

## Trigger

Subscriptions is opened before any expense was marked recurring.

## Outcome

No subscriptions yet explains that marking an expense as recurring adds it here.
