---
kind: primary
routes:
  app: Android app
steps:
  - text: "The Period end time comes after the Budget period finish date"
    kind: condition
    unattended: true
    entities:
      - { entity: budget-period, effect: reads, facts: [Finish date] }
      - { entity: app-settings, effect: reads, facts: [Period end time] }
    contexts:
      app:
        place: android-app::period-end-notification
  - text: "The Product posts the period end notification with what was left or overspent"
    kind: product
    entities:
      - { entity: budget-period, effect: reads, facts: [Remaining] }
    contexts:
      app:
        place: android-app::period-end-notification
---

# Notify that the period finished

## Trigger

The period is over and the chosen time of day arrives.

## Outcome

The notification says the period ended with an amount remaining, an extra amount spent, or nothing spent.

## Edge cases

- Without the exact alarm permission Android may deliver it later than the chosen time.
- Changing the Period end time moves the notification to the new time.
