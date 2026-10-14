---
kind: primary
routes:
  app: Android app
steps:
  - text: "No Budget period exists yet, so the budget sheet opens in setup"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The User enters the total budget, picks the start and finish dates and the currency"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::budget-period
  - text: "The User chooses the End of period surplus and the Daily amount and taps Apply"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product starts the Budget period and schedules its end-of-period notification"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: creates, to: "Active", facts: [Total budget, Start date, Finish date, Currency, End of period surplus, Daily amount, Carried in, Leftover choices, Finished early on, Spent, Pending extra money, Remaining] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "Home shows what can be spent today"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Remaining] }
    contexts:
      app:
        place: android-app::home
---

# Set up the first budget

## Trigger

The User has just completed the welcome, or has no budget yet.

## Outcome

An active budget period exists and the budget pill shows the first day's allowance.
