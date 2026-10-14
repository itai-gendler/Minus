---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User covers the top of the phone for about a second while Home is open"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product blurs every amount"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Privacy mode] }
    contexts:
      app:
        place: android-app::home
---

# Turn on privacy mode by covering the phone

## Trigger

The User needs to hide the numbers quickly.

## Outcome

Amounts are blurred and Privacy mode enabled is shown.
