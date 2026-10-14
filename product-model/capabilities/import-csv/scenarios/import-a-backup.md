---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User taps Import CSV in Settings and picks a file"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
  - text: "The Product creates any Category the file names that does not exist yet"
    kind: product
    actor: user
    entities:
      - { entity: category, effect: creates, to: "Active", facts: [Name, Usage] }
    contexts:
      app:
        place: android-app::settings
  - text: "The Product adds each Expense row of the file"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::settings
  - text: "The Product adds the file's past Budget period rows"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: creates, to: "Past", facts: [Total budget, Start date, Finish date, Currency, Spent] }
    contexts:
      app:
        place: android-app::settings
---

# Import a backup

## Trigger

The User moves to a new phone or restores a backup.

## Outcome

The expenses and past periods of the file are in Minus.

## Edge cases

- Rows with an id replace the expense holding that id; rows without one are added, so importing the same rows twice counts them twice.
