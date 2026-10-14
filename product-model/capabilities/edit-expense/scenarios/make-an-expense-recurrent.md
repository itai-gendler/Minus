---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User opens an Expense in the history and turns on Make recurrent"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount, Category] }
    contexts:
      app:
        place: android-app::history
  - text: "The User sets the frequency, billing day and recurrence end and taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::history
  - text: "The Product turns the Expense into a Recurring expense"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: removes, from: "Recorded" }
      - { entity: recurring-expense, effect: creates, facts: [Amount, Category, Frequency, Billing day, First charge, Recurrence end, Paid with credit card] }
    contexts:
      app:
        place: android-app::history
---

# Make an expense recurrent

## Trigger

An expense the User recorded once turns out to repeat.

## Outcome

The expense now repeats as a recurring expense, with reminders, and appears in Subscriptions.
