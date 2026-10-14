---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User taps Back up data in Settings"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
  - text: "The Product writes every Expense, Recurring expense and Budget period to a CSV file in Downloads"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: recurring-expense, effect: reads, facts: [Amount, Category, Frequency, Billing day, First charge, Recurrence end, Paid with credit card] }
      - { entity: budget-period, effect: reads, facts: [Total budget, Start date, Finish date, Currency, Spent] }
    contexts:
      app:
        place: android-app::settings
  - text: "The Product confirms Export saved to Downloads and offers to share the file"
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
---

# Back up data

## Trigger

The User wants a copy of their data.

## Outcome

A file named after the period number and dates is in Downloads and can be shared.

## Edge cases

- When the file cannot be saved to Downloads, it is offered for sharing only; if that fails too, Failed to export CSV is shown.
