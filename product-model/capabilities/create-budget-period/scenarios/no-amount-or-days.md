---
kind: validation
routes:
  app: Android app
steps:
  - text: "The User leaves the total at zero or picks no finish date"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product shows why the Budget period cannot be applied and keeps Apply unavailable"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::budget-period
---

# A budget without an amount or a finish date

## Trigger

The budget editor is incomplete.

## Outcome

Budget must be greater than 0, or No days defined, is shown and nothing is saved.
