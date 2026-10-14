---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User chooses Discard remaining budget"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Pending extra money] }
    contexts:
      app:
        place: android-app::period-finished
  - text: "The Product drops the pending money"
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

# Discard the remaining budget

## Trigger

The User does not want the leftover in the next budget.

## Outcome

Nothing carries over and the next period starts with the total entered.
