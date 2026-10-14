---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User reads the welcome and taps Continue"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::onboarding
  - text: "The Product records that onboarding is completed and opens Home with the budget setup"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Onboarding completed] }
    contexts:
      app:
        place: android-app::home
---

# Continue from the welcome

## Trigger

Minus is opened for the first time.

## Outcome

The welcome is not shown again and the budget sheet asks for the first budget (create-budget-period).
