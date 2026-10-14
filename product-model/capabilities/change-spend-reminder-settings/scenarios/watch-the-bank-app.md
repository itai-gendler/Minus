---
kind: primary
routes:
  app: Android app
steps:
  - text: "Minus has notification access"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::spend-reminders
  - text: "The User turns on Watch notifications and selects the bank app"
    kind: actor
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Spend reminders, Apps to watch] }
    contexts:
      app:
        place: android-app::spend-reminders
  - text: "The Product saves the App settings"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Spend reminders, Apps to watch] }
    contexts:
      app:
        place: android-app::spend-reminders
---

# Watch the bank app

## Trigger

The User wants reminders when the bank notifies a charge.

## Outcome

New notifications of the selected apps are read for charges (spot-spend-in-notifications).

## Edge cases

- With no app selected, the screen asks to pick at least one.
