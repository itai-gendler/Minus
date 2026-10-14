---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User chooses Add to today on the Period finished question"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Pending extra money] }
    contexts:
      app:
        place: android-app::period-finished
  - text: "The Product keeps the money for the first day of the next Budget period"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: changes, facts: [Pending extra money] }
    contexts:
      app:
        place: android-app::period-finished
  - text: "The Product opens the finished period's analytics"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Spent] }
    contexts:
      app:
        place: android-app::analytics
---

# Add the remaining money to today

## Trigger

The User wants a bigger first day.

## Outcome

When the next period starts, the whole amount is added to its first day.
