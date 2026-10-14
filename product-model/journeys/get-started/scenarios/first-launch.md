---
kind: primary
result: achieved
routes:
  app: Android app
steps:
  - text: "The User reads the welcome and taps Continue"
    kind: actor
    capability: complete-onboarding
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::onboarding
  - text: "The Product records that onboarding is completed and opens Home with the budget setup"
    kind: product
    capability: complete-onboarding
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Onboarding completed] }
    contexts:
      app:
        place: android-app::home
  - text: "The User enters the total, dates, currency and behavior and taps Apply"
    kind: actor
    capability: create-budget-period
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product starts the Budget period"
    kind: product
    capability: create-budget-period
    actor: user
    entities:
      - { entity: budget-period, effect: creates, to: "Active", facts: [Total budget, Start date, Finish date, Currency, End of period surplus, Daily amount, Carried in, Leftover choices, Finished early on, Spent, Pending extra money, Remaining] }
    contexts:
      app:
        place: android-app::budget-period
---

# From the welcome to the first budget

## Trigger

Minus is opened for the first time.

## Outcome

The welcome is done and the first budget period is active.
