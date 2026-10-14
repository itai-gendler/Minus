---
kind: edge
routes:
  app: Android app
steps:
  - text: "No Budget period exists"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
  - text: "The User taps Set up your budget on the pill"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
---

# No budget yet

## Trigger

The pill is checked before any budget was set up.

## Outcome

The pill says No budget and opens the budget setup; the watch says No budget set on the phone yet.
