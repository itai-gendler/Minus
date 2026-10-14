---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User taps Mark as paid on the payment reminder"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount, Category] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
  - text: "The Product settles the Recurring payment as paid and records an Expense for it"
    kind: product
    actor: user
    entities:
      - { entity: recurring-payment, effect: creates, to: "Paid", facts: [Due date] }
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
---

# Mark a payment as paid from its reminder

## Trigger

The reminder arrives on the due date.

## Outcome

The notification closes and the payment is settled without opening the app.
