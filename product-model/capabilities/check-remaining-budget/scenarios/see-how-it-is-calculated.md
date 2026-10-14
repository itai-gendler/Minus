---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User holds the budget pill"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The User reads how the Budget period amount is made up"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Total budget, Spent, Remaining, Carried in] }
    contexts:
      app:
        place: android-app::budget-period
---

# See how the amount is calculated

## Trigger

The User wonders where the amount comes from.

## Outcome

How it's calculated lists the budget remaining, income and deductions, recurring payments charged, what was spent and any surplus carried in.
