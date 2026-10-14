---
kind: alternative
routes:
  app: Android app
steps:
  - text: "A Sync folder holding a Minus copy is set while Minus keeps no budget and no Expense"
    kind: condition
    unattended: true
    entities:
      - { entity: app-settings, effect: reads, facts: [Sync folder] }
      - { entity: expense, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::csv-folder-sync
  - text: "The Product restores the Budget period from the copy instead of overwriting it"
    kind: product
    entities:
      - { entity: budget-period, effect: creates, to: "Active", facts: [Total budget, Start date, Finish date, Currency, End of period surplus, Daily amount, Carried in, Leftover choices, Finished early on, Spent, Pending extra money, Remaining] }
    contexts:
      app:
        place: android-app::csv-folder-sync
  - text: "The Product restores every Expense from the copy and records the last sync"
    kind: product
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: app-settings, effect: changes, facts: [Last sync] }
    contexts:
      app:
        place: android-app::csv-folder-sync
---

# Restore from the folder into an empty app

## Trigger

Minus was reinstalled and pointed at its old folder.

## Outcome

The data comes back and the status says Restored from the folder.
