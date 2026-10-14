---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User taps the add widget or the New Transaction tile"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home-screen-widgets
  - text: "The User types the amount on Home and taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the Expense in the active Budget period"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
---

# Record from a widget or the tile

## Trigger

The User wants to record an expense without first opening the app.

## Outcome

Minus opens on the numpad and the expense is recorded as on Home.
