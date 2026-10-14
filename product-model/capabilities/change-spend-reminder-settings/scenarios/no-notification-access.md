---
kind: validation
routes:
  app: Android app
steps:
  - text: "Minus does not have notification access"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::spend-reminders
  - text: "The User taps Open notification access"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::spend-reminders
---

# Notification access missing

## Trigger

Android has not allowed Minus to read notifications.

## Outcome

Android's notification access settings open; reminders work once access is granted.
