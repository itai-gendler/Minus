---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The Budget period has ended or was finalized early"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Finished early on, Finish date] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The User reads the Period finished summary of what was spent and saved"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Spent, Total budget] }
    contexts:
      app:
        place: android-app::analytics
---

# Review a finished period

## Trigger

Analytics opens after the period ended.

## Outcome

The summary says whether nothing was spent, the budget was exceeded, or what was saved, and offers New budget.
