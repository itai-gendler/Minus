---
kind: alternative
routes:
  app: Android app
steps:
  - text: "A Recurring expense charge falls due in three days"
    kind: condition
    unattended: true
    entities:
      - { entity: recurring-expense, effect: reads, facts: [First charge, Billing day] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
  - text: "The Product posts an upcoming reminder saying when it will be charged"
    kind: product
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount, Category] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
---

# A payment comes up in three days

## Trigger

Three days remain before a charge.

## Outcome

The person is told to prepare for the charge.
