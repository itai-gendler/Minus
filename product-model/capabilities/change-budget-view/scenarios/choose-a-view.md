---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens the budget sheet and picks Weekly"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product remembers the Budget view"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Budget view] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The budget pill shows what is left this week of the Budget period"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Remaining] }
    contexts:
      app:
        place: android-app::home
---

# Choose how to view the budget

## Trigger

The User thinks of their money by the week.

## Outcome

The pill, the widgets and the breakdown use the weekly allowance.
