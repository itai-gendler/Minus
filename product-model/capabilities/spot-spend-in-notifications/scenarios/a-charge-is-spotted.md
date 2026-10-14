---
kind: primary
routes:
  app: Android app
steps:
  - text: "A watched app posts a notification with an amount in the Budget period currency"
    kind: condition
    unattended: true
    entities:
      - { entity: budget-period, effect: reads, facts: [Currency] }
      - { entity: app-settings, effect: reads, facts: [Spend reminders, Apps to watch] }
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The Product posts a spend reminder with the amount, Minus it and Save as is"
    kind: product
    entities: []
    contexts:
      app:
        place: android-app::spend-reminder-notification
---

# A charge is spotted

## Trigger

The bank app notifies a card payment in the budget's currency.

## Outcome

A spend reminder offers to record the amount.
