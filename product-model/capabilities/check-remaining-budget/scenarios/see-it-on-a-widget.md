---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User looks at a Minus widget on the home screen"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Remaining, Spent, Total budget, Finish date] }
    contexts:
      app:
        place: android-app::home-screen-widgets
---

# See it on a widget

## Trigger

The User wants the budget at a glance without opening the app.

## Outcome

The widget shows the remaining amount, spending or the days countdown, kept up to date as expenses change.
