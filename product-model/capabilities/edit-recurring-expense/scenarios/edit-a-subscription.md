---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens a Recurring expense in Subscriptions and taps edit"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount, Frequency] }
    contexts:
      app:
        place: android-app::subscriptions
  - text: "The User changes its amount, name, frequency, billing day or recurrence end and saves"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::subscriptions
  - text: "The Product saves the Recurring expense and reschedules its reminders"
    kind: product
    actor: user
    entities:
      - { entity: recurring-expense, effect: changes, facts: [Amount, Category, Frequency, Billing day, Recurrence end, Paid with credit card] }
    contexts:
      app:
        place: android-app::subscriptions
---

# Edit a subscription

## Trigger

A subscription's price or billing day changed.

## Outcome

Future charges and reminders follow the new values.

## Edge cases

- If the change cannot be saved, Could not save this change is shown.
