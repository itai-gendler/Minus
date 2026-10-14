---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User taps Undo on the Saved to Minus notification"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount] }
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The Product deletes the Expense that was quick-saved"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: removes, from: "Recorded" }
    contexts:
      app:
        place: android-app::spend-reminder-notification
---

# Undo a quick save

## Trigger

A spotted charge was saved as is by mistake.

## Outcome

The notification closes and the saved expense is deleted.
