---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens the Category picker on Home and chooses Add New Category"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
  - text: "The User types the name and saves it"
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
---

# Add a new category

## Trigger

The User wants a category ready before using it.

## Outcome

The category is offered in the picker from now on.
