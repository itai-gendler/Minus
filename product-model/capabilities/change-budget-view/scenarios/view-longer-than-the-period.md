---
kind: edge
routes:
  app: Android app
steps:
  - text: "The User opens the budget sheet of a short Budget period"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Start date, Finish date] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Budget period lasts fewer days than the chosen view"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Start date, Finish date] }
      - { entity: app-settings, effect: reads, facts: [Budget view] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product switches to the longest view that fits"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Budget view] }
    contexts:
      app:
        place: android-app::budget-period
---

# A view longer than the period

## Trigger

A ten-day period while the view was Monthly.

## Outcome

Monthly is not offered and Weekly is used instead.
