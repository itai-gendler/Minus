---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User taps Skip on a Recurring expense due today"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount, Category] }
    contexts:
      app:
        place: android-app::subscriptions
  - text: "The Product settles the Recurring payment as skipped"
    kind: product
    actor: user
    entities:
      - { entity: recurring-payment, effect: creates, to: "Skipped", facts: [Due date] }
    contexts:
      app:
        place: android-app::subscriptions
---

# Skip a payment in Subscriptions

## Trigger

A charge did not happen this time.

## Outcome

The charge shows as Skipped and no longer counts against the budget.

## Edge cases

- If it cannot be skipped, Could not skip this payment is shown.
