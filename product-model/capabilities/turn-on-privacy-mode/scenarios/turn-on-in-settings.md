---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User turns on Privacy mode in Settings"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
  - text: "The Product blurs every amount and says Privacy mode enabled"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Privacy mode] }
    contexts:
      app:
        place: android-app::settings
---

# Turn on privacy mode in Settings

## Trigger

Someone else can see the screen.

## Outcome

Amounts are blurred everywhere in the app until privacy mode is turned off.
