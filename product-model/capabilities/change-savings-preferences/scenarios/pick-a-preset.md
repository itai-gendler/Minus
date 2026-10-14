---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens Savings preferences and picks a split preset"
    kind: actor
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Savings split] }
    contexts:
      app:
        place: android-app::settings
  - text: "The User enters a target amount and months and saves"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
  - text: "The Product saves the App settings savings preferences"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Savings split, Savings goal] }
    contexts:
      app:
        place: android-app::settings
---

# Pick a split and a goal

## Trigger

The User wants recommendations that match their situation.

## Outcome

The savings recommendation shows how much to save per period to reach the goal.
