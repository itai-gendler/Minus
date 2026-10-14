---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User turns on Recurrent, types the amount and a name and taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The User chooses Weekly or Biweekly and the limit date and confirms"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product saves the Recurring expense, first charged today"
    kind: product
    actor: user
    entities:
      - { entity: recurring-expense, effect: creates, facts: [Amount, Category, Frequency, Billing day, First charge, Recurrence end, Paid with credit card] }
    contexts:
      app:
        place: android-app::home
---

# Add a weekly or biweekly expense

## Trigger

The expense repeats every week or two.

## Outcome

It is charged today and every seven or fourteen days until the limit date.
