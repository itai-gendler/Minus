---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens the history"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::history
  - text: "The User reads each Expense with its details, grouped by date"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount, Category, Date] }
    contexts:
      app:
        place: android-app::history
  - text: "The User reads the Recurring expense charges of this period and the upcoming ones"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Amount, Category, Frequency] }
    contexts:
      app:
        place: android-app::history
---

# Browse the period's expenses

## Trigger

The User wants to see where the period's money went.

## Outcome

The latest day is expanded and every recorded expense and recurring charge of the period is listed.

## Edge cases

- With no expenses yet, No recorded expenses invites adding one.
