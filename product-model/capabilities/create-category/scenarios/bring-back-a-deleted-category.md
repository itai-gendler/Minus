---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User adds a Category with the name of a deleted one"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: reads, facts: [Name] }
    contexts:
      app:
        place: android-app::home
  - text: "The Product offers the Category again"
    kind: product
    actor: user
    entities:
      - { entity: category, effect: changes, from: "Deleted", to: "Active", facts: [] }
    contexts:
      app:
        place: android-app::home
---

# Bring back a deleted category

## Trigger

The User needs a category they deleted earlier.

## Outcome

The same category is offered again; no second category with that name exists.

## Edge cases

- Recording an expense under a deleted category's name brings it back the same way.
