---
kind: validation
routes:
  app: Android app
steps:
  - text: "The User confirms changing an Expense of a past period"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The biometric unlock fails or is cancelled"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::analytics
---

# Unlocking a past period fails

## Trigger

The fingerprint does not match or the prompt is cancelled.

## Outcome

Nothing changes and the error is shown briefly.
