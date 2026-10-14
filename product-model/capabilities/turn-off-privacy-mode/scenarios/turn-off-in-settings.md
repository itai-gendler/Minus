---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User turns off Privacy mode in Settings"
    kind: actor
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Privacy mode] }
    contexts:
      app:
        place: android-app::settings
  - text: "The Product shows the amounts again"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Privacy mode] }
    contexts:
      app:
        place: android-app::settings
---

# Turn off privacy mode in Settings

## Trigger

Settings shows the Privacy mode activated card.

## Outcome

Amounts are visible again.
