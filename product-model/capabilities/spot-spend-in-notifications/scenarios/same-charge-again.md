---
kind: edge
routes:
  app: Android app
steps:
  - text: "A watched app notifies the same amount again within a minute"
    kind: condition
    unattended: true
    entities: []
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The Product posts no second spend reminder"
    kind: product
    entities: []
    contexts:
      app:
        place: android-app::spend-reminder-notification
---

# The same charge notified twice

## Trigger

An app repeats or updates the same notification.

## Outcome

Only one spend reminder is shown for it.

## Edge cases

- At most ten spend reminders are posted in an hour.
