---
kind: edge
routes:
  app: Android app
steps:
  - text: "The User imports a file with rows lacking a valid date or a positive amount"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
  - text: "The Product skips those rows and imports the rest"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::settings
---

# Some rows are rejected

## Trigger

The file was written by hand or by another tool.

## Outcome

Valid rows are imported; each rejected row is skipped on its own.
