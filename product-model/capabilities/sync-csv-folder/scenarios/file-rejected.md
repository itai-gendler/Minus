---
kind: edge
routes:
  app: Android app
steps:
  - text: "A minus_import file in the Sync folder has rows that cannot be read"
    kind: condition
    unattended: true
    entities:
      - { entity: app-settings, effect: reads, facts: [Sync folder] }
    contexts:
      app:
        place: android-app::csv-folder-sync
  - text: "The Product imports its good rows as an Expense each and renames the file to .rejected"
    kind: product
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: app-settings, effect: changes, facts: [Last sync] }
    contexts:
      app:
        place: android-app::csv-folder-sync
---

# An import file has bad rows

## Trigger

An outside tool wrote some invalid rows.

## Outcome

The status names the rejected file; the file stays in the folder for inspection and is not read again.
