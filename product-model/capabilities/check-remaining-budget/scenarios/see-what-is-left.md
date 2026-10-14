---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User reads the budget pill on Home"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Remaining] }
    contexts:
      app:
        place: android-app::home
---

# See what is left

## Trigger

The User wants to know what they can still spend.

## Outcome

The pill shows what is left today, this week, these two weeks or this month by the chosen view, and what the next one will be.

## Edge cases

- When the allowance is spent, the pill says the daily, weekly or biweekly amount was exceeded.
