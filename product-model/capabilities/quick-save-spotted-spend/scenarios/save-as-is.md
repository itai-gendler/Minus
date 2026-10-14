---
kind: primary
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
  - text: "The Product records the Expense with the app's name as its extra note"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The notification says the Expense was saved as is and offers Undo"
    kind: condition
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount] }
    contexts:
      app:
        place: android-app::spend-reminder-notification
---

# Save a spotted charge as is

## Trigger

The User wants the charge counted without opening the app.

## Outcome

The expense is recorded today in the active period.
