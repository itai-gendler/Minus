---
kind: primary
routes:
  app: Android app
steps:
  - text: "A Recurring expense charge falls due today at the chosen reminder time"
    kind: condition
    unattended: true
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Frequency, Billing day, First charge, Recurrence end] }
      - { entity: app-settings, effect: reads, facts: [Recurring payments time] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
  - text: "The Product posts the reminder with the amount, Mark as paid and Skip"
    kind: product
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount, Category, Frequency] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
---

# A payment is due today

## Trigger

The billing day of a subscription arrives.

## Outcome

One reminder says the payment is due today, and the next charge is scheduled.
