---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User changes the Credit card cutoff day in the credit card section"
    kind: actor
    actor: user
    entities:
      - { entity: credit-card, effect: reads, facts: [Cutoff day] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The Product saves the Credit card cutoff day and reschedules the payment reminder"
    kind: product
    actor: user
    entities:
      - { entity: credit-card, effect: changes, facts: [Cutoff day] }
    contexts:
      app:
        place: android-app::analytics
---

# Change the cutoff day in Analytics

## Trigger

The bank moved the billing cutoff.

## Outcome

The due date and the reminder follow the new cutoff day.
