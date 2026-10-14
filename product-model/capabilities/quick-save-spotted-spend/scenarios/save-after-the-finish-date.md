---
kind: edge
routes:
  app: Android app
steps:
  - text: "The User taps Save as is on a spend reminder"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The active Budget period's finish date has passed"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Finish date] }
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The Product keeps the Expense for the next period"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Queued for next period", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::spend-reminder-notification
---

# Save a spotted charge after the finish date

## Trigger

The period ended and no new one has started.

## Outcome

The notification says the amount was saved for the next period, without Undo.
