---
kind: edge
routes:
  app: Android app
steps:
  - text: "The User taps Save as is twice on the same spend reminder"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The Product records the Expense once"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::spend-reminder-notification
---

# Save as is tapped twice

## Trigger

A double tap or a repeated delivery of the same action.

## Outcome

Only one expense is recorded for that reminder.
