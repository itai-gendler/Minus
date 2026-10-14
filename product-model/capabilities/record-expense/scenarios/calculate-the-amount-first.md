---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User swipes up the numpad and types a calculation such as 12+8.5"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product evaluates the calculation"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The User taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the Expense with the result as its amount"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
---

# Calculate the amount before saving

## Trigger

The User needs to add up several amounts before saving.

## Outcome

One expense is recorded for the calculated total.
