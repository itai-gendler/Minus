---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User imports a file that carries the active period's settings"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
  - text: "The Product restores the active Budget period from the file and marks onboarding completed"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: changes, facts: [Total budget, Start date, Finish date, Currency, End of period surplus, Daily amount] }
      - { entity: app-settings, effect: changes, facts: [Onboarding completed] }
    contexts:
      app:
        place: android-app::settings
---

# Import restores the active budget

## Trigger

The file was exported by Minus with a budget set up.

## Outcome

The budget, its dates and behavior are as they were when exported.
