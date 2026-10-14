---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User turns on the Credit card mark of an entry in the history before any cutoff day is set"
    kind: actor
    actor: user
    entities:
      - { entity: credit-card, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::history
  - text: "The User enters the cutoff day and confirms"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::history
  - text: "The Product saves the Credit card cutoff day"
    kind: product
    actor: user
    entities:
      - { entity: credit-card, effect: changes, facts: [Cutoff day] }
    contexts:
      app:
        place: android-app::history
---

# Set the cutoff day while editing an expense

## Trigger

An expense is corrected to say it was paid with the card.

## Outcome

The cutoff day is set and the mark can be saved.
