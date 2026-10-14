---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User deletes a repeating charge in a past period's breakdown after unlocking"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::analytics
  - text: "The Product settles that Recurring payment as skipped"
    kind: product
    actor: user
    entities:
      - { entity: recurring-payment, effect: creates, to: "Skipped", facts: [Due date] }
    contexts:
      app:
        place: android-app::analytics
---

# Remove a recurring charge from a past period

## Trigger

A past period shows a recurring charge that did not happen.

## Outcome

The past period no longer counts it.
