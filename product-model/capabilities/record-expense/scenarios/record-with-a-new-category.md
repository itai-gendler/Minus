---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User types the amount and a Category name not used before"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: reads, facts: [] }
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
  - text: "The Product creates the Category"
    kind: product
    actor: user
    entities:
      - { entity: category, effect: creates, to: "Active", facts: [Name, Usage] }
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the Expense under it"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::home
---

# Record an expense under a new category

## Trigger

The User types a category name that does not exist yet.

## Outcome

A new category with that name exists and the expense is recorded under it.
