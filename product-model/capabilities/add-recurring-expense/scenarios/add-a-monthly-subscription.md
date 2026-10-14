---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User turns on Recurrent, types the amount and a name such as Gym, and taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The User chooses Monthly, the billing day and the limit date and confirms"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product saves the Recurring expense and schedules its reminders"
    kind: product
    actor: user
    entities:
      - { entity: recurring-expense, effect: creates, facts: [Amount, Category, Frequency, Billing day, First charge, Recurrence end, Paid with credit card] }
    contexts:
      app:
        place: android-app::home
---

# Add a monthly subscription

## Trigger

The User starts paying for something every month.

## Outcome

The subscription is charged on its billing day each month until the limit date and appears in Subscriptions.

## Edge cases

- With no category typed, the recurring expense is named after its frequency, such as Monthly subscription without name.
- The limit date starts three months after the period's finish date unless changed.
