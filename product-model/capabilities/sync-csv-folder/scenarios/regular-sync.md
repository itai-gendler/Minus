---
kind: primary
routes:
  app: Android app
steps:
  - text: "Two hours have passed since the last sync and a Sync folder is set"
    kind: condition
    unattended: true
    entities:
      - { entity: app-settings, effect: reads, facts: [Sync folder] }
    contexts:
      app:
        place: android-app::csv-folder-sync
  - text: "The Product imports each minus_import file as an Expense and renames the file to .imported"
    kind: product
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      app:
        place: android-app::csv-folder-sync
  - text: "The Product writes the CSV copy of every Expense and Budget period and records the last sync"
    kind: product
    entities:
      - { entity: expense, effect: reads, facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [Total budget, Start date, Finish date, Spent] }
      - { entity: app-settings, effect: changes, facts: [Last sync] }
    contexts:
      app:
        place: android-app::csv-folder-sync
---

# A regular sync

## Trigger

The sync interval comes due.

## Outcome

New rows from outside tools are in Minus and the folder holds an up-to-date copy; the status says Last sync and how many rows were imported.
