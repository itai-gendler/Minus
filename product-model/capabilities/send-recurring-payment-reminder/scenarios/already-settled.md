---
kind: edge
routes:
  app: Android app
steps:
  - text: "A Recurring expense charge comes due that was already marked paid or skipped"
    kind: condition
    unattended: true
    entities:
      - { entity: recurring-expense, effect: reads, facts: [] }
      - { entity: recurring-payment, effect: reads, facts: [Due date] }
    contexts:
      app:
        place: android-app::recurring-payment-notification
  - text: "The Product posts no reminder for it"
    kind: product
    entities: []
    contexts:
      app:
        place: android-app::recurring-payment-notification
---

# A payment already settled

## Trigger

The person settled the charge ahead of time.

## Outcome

No reminder comes for that charge; the next one is reminded as usual.

## Edge cases

- No reminder comes after the recurrence end, or for a deleted recurring expense.
