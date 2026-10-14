---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens Subscriptions"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::subscriptions
  - text: "The User reads the monthly commitment and each Recurring expense due soon or upcoming"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount, Category, Frequency, Billing day] }
    contexts:
      app:
        place: android-app::subscriptions
  - text: "The User reads the Budget period's charges by day with each Recurring payment's status"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Total budget] }
      - { entity: recurring-payment, effect: reads, facts: [Due date] }
    contexts:
      app:
        place: android-app::subscriptions
---

# Review subscriptions

## Trigger

The User wants to know what their subscriptions cost and when they are charged.

## Outcome

Weekly and biweekly charges are converted into a monthly commitment, and the share of the period's budget they take is shown.

## Edge cases

- A past charge never settled shows as paid in the calendar.
