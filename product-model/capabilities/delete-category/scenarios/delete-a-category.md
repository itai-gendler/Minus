---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens the category picker and taps Delete Category on a Category"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: reads, facts: [Name] }
    contexts:
      app:
        place: android-app::home
  - text: "The Product stops offering the Category"
    kind: product
    actor: user
    entities:
      - { entity: category, effect: changes, from: "Active", to: "Deleted", facts: [] }
    contexts:
      app:
        place: android-app::home
---

# Delete a category

## Trigger

A category is no longer wanted in the suggestions.

## Outcome

The category disappears from the picker; expenses already saved with it keep its name.
