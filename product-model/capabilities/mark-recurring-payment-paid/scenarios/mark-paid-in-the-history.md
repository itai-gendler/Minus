---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User taps Mark as paid on a Recurring expense charge of this period"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount] }
    contexts:
      app:
        place: android-app::history
  - text: "The Product settles the Recurring payment as paid and records an Expense for it"
    kind: product
    actor: user
    entities:
      - { entity: recurring-payment, effect: creates, to: "Paid", facts: [Due date] }
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::history
---

# Mark a payment as paid in the history

## Trigger

The User reviews the period's recurring payments.

## Outcome

The charge is settled and recorded.
