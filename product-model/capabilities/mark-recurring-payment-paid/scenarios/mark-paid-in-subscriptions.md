---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User taps Mark as paid on a Recurring expense due today"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount, Category] }
    contexts:
      app:
        place: android-app::subscriptions
  - text: "The Product settles the Recurring payment as paid and records an Expense for it in the active Budget period"
    kind: product
    actor: user
    entities:
      - { entity: recurring-payment, effect: creates, to: "Paid", facts: [Due date] }
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::subscriptions
---

# Mark a payment as paid in Subscriptions

## Trigger

A subscription was charged today.

## Outcome

The charge shows as Paid, an expense with its amount and category is recorded, and no reminder comes for it.

## Edge cases

- If it cannot be confirmed, Could not confirm this payment is shown.
