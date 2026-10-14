---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User taps Skip on the payment reminder"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
  - text: "The Product settles the Recurring payment as skipped and schedules the next reminder"
    kind: product
    actor: user
    entities:
      - { entity: recurring-payment, effect: creates, to: "Skipped", facts: [Due date] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
---

# Skip a payment from its reminder

## Trigger

The reminder arrives for a charge that will not happen.

## Outcome

The notification closes and the next charge is reminded as usual.
