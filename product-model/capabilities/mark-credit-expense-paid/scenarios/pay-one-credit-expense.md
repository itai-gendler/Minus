---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens the credit card section and taps pay on an Expense"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount, Paid with credit card] }
      - { entity: credit-card, effect: reads, facts: [Total owed] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The Product marks the Expense as paid on the card"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: changes, facts: [Credit paid] }
    contexts:
      app:
        place: android-app::analytics
---

# Mark one credit expense as paid

## Trigger

The User paid part of the card.

## Outcome

The expense no longer counts in the total owed.
