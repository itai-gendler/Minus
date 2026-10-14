---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User reads what is left of the ended Budget period"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Pending extra money, Spent] }
    contexts:
      app:
        place: android-app::period-finished
  - text: "The User chooses Split equally"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::period-finished
  - text: "The Product keeps the money to spread over the next Budget period's days"
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

# Split the remaining money equally

## Trigger

A period ended with money left and End of period surplus is Ask me.

## Outcome

When the next period starts, the money is added to its total and spread over its days.
