---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User picks a past Budget period in Past periods"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Start date, Finish date] }
    contexts:
      app:
        place: android-app::past-periods
  - text: "The User reads that period's spending and each Expense"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Spent, Total budget] }
      - { entity: expense, effect: reads, facts: [Amount, Category, Date] }
    contexts:
      app:
        place: android-app::analytics
---

# Review a past period

## Trigger

The User compares with an earlier period.

## Outcome

Analytics shows the chosen past period; closing returns to the current one.
