---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens the budget sheet from the budget pill and taps Edit Budget"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Total budget, Start date, Finish date] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The User changes the total, dates, currency or behavior and taps Apply"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product saves the active Budget period and reschedules its end-of-period notification"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: changes, facts: [Total budget, Start date, Finish date, Currency, End of period surplus, Daily amount] }
    contexts:
      app:
        place: android-app::budget-period
---

# Edit the active period

## Trigger

The User's budget or dates changed during the period.

## Outcome

The active period keeps its expenses and its allowance is recalculated from the new values.
