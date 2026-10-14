---
kind: edge
routes:
  app: Android app
steps:
  - text: "The Credit card payment due date is three days away and every credit Expense is paid"
    kind: condition
    unattended: true
    entities:
      - { entity: credit-card, effect: reads, facts: [Total owed] }
      - { entity: expense, effect: reads, facts: [Credit paid] }
    contexts:
      app:
        place: android-app::credit-card-payment-notification
  - text: "The Product posts no reminder"
    kind: product
    entities: []
    contexts:
      app:
        place: android-app::credit-card-payment-notification
---

# Nothing is owed

## Trigger

All credit card expenses up to the cutoff are marked paid.

## Outcome

No reminder comes.
