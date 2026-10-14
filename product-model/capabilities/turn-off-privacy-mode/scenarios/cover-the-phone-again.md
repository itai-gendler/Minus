---
kind: primary
routes:
  app: Android app
steps:
  - text: "Privacy mode is on"
    kind: condition
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Privacy mode] }
    contexts:
      app:
        place: android-app::home
  - text: "The User covers the top of the phone for about a second"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product shows the amounts again and says Privacy mode disabled"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Privacy mode] }
    contexts:
      app:
        place: android-app::home
---

# Turn off privacy mode by covering the phone

## Trigger

The User wants to see the numbers again.

## Outcome

Amounts are visible again.
