---
kind: edge
routes:
  app: Android app
steps:
  - text: "The User dismisses the recurrence details without confirming"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product saves nothing"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
---

# Cancel the recurrence details

## Trigger

The User changes their mind about the recurring expense.

## Outcome

No recurring expense is saved and the amount stays on the numpad.
