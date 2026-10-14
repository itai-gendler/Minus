---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User taps Mark all as paid in the credit card section"
    kind: actor
    actor: user
    entities:
      - { entity: credit-card, effect: reads, facts: [Total owed] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The Product marks every unpaid card Expense as paid"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: changes, facts: [Credit paid] }
    contexts:
      app:
        place: android-app::analytics
---

# Mark all credit expenses as paid

## Trigger

The User paid the card in full.

## Outcome

Marked all as paid is confirmed and nothing is owed.
