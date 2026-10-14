---
kind: validation
routes:
  app: Android app
steps:
  - text: "The User taps Done with no amount or an amount of zero"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product records nothing"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
---

# Nothing to record

## Trigger

Done is tapped without a usable amount.

## Outcome

No expense is recorded and the numpad stays as it was.
