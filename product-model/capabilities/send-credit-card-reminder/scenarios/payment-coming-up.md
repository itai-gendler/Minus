---
kind: primary
routes:
  app: Android app
steps:
  - text: "The Credit card payment due date is three days away and something is owed"
    kind: condition
    unattended: true
    entities:
      - { entity: credit-card, effect: reads, facts: [Cutoff day, Payment due date, Total owed] }
    contexts:
      app:
        place: android-app::credit-card-payment-notification
  - text: "The Product posts Upcoming credit card payment with the due date and the amount to pay"
    kind: product
    entities:
      - { entity: credit-card, effect: reads, facts: [Payment due date, Total owed] }
    contexts:
      app:
        place: android-app::credit-card-payment-notification
---

# A credit card payment is coming up

## Trigger

A cutoff day is set and the due date approaches.

## Outcome

One reminder per due date says what to pay and by when.
