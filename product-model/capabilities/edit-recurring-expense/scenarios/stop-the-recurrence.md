---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User edits a Recurring expense in the history and turns recurrence off"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount] }
    contexts:
      app:
        place: android-app::history
  - text: "The User taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::history
  - text: "The Product keeps it as a one-time Expense and cancels its reminders"
    kind: product
    actor: user
    entities:
      - { entity: recurring-expense, effect: removes }
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::history
---

# Turn a recurring expense into a one-time expense

## Trigger

Something marked recurring only happened once.

## Outcome

It no longer repeats and counts once, on its date.
