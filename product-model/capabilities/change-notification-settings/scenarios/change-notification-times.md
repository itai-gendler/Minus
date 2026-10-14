---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens Settings and picks a new time for the period end or for recurring charges"
    kind: actor
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Period end time, Recurring payments time] }
    contexts:
      app:
        place: android-app::settings
  - text: "The Product saves the App settings times and reschedules the reminders"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Period end time, Recurring payments time] }
    contexts:
      app:
        place: android-app::settings
---

# Change the notification times

## Trigger

Reminders come at an inconvenient time.

## Outcome

The period end notification, recurring payment reminders and the credit card reminder use the new times.
