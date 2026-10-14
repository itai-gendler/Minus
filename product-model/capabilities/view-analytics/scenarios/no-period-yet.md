---
kind: edge
routes:
  app: Android app
steps:
  - text: "The User opens Analytics"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::analytics
  - text: "No Budget period exists"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::analytics
---

# No budget period yet

## Trigger

Analytics is opened before any budget was set up.

## Outcome

No budget period yet invites creating one.
