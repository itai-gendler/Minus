---
kind: edge
routes:
  app: Android app
steps:
  - text: "The User types an amount and taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The active Budget period's finish date has passed and no new period has started"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Finish date] }
    contexts:
      app:
        place: android-app::home
  - text: "The Product keeps the Expense for the next period"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Queued for next period", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::home
---

# Record an expense after the finish date

## Trigger

The User records spending after the period's last day, before setting up the next period.

## Outcome

The expense waits, with the message Expense queued for next period, and joins the next period when it starts.
