---
kind: validation
routes:
  app: Android app
steps:
  - text: "The User confirms deleting a past Budget period"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Start date] }
    contexts:
      app:
        place: android-app::past-periods
  - text: "The biometric unlock fails or is cancelled"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::past-periods
---

# Unlocking fails

## Trigger

The fingerprint does not match or the prompt is cancelled.

## Outcome

Nothing is deleted.
