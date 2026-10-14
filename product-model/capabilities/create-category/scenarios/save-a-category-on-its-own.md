---
kind: alternative
routes:
  app: Android app
steps:
  - text: "Save categories on their own is on in Extra features"
    kind: condition
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Save categories on their own] }
    contexts:
      app:
        place: android-app::home
  - text: "The User taps the New category tag on Home, types a name and saves it"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
  - text: "The Product creates the Category and confirms New category saved"
    kind: product
    actor: user
    entities:
      - { entity: category, effect: creates, to: "Active", facts: [Name, Usage] }
    contexts:
      app:
        place: android-app::home
---

# Save a category on its own

## Trigger

The User wants to prepare categories with no amount attached.

## Outcome

The category exists with no expense recorded.
