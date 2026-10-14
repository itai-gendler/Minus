---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User taps Sync folder and picks a folder"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
  - text: "The Product saves the App settings sync folder and syncs now"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Sync folder] }
    contexts:
      app:
        place: android-app::settings
  - text: "Settings shows that Minus syncs to the folder every two hours"
    kind: condition
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Sync folder, Last sync] }
    contexts:
      app:
        place: android-app::settings
---

# Pick a sync folder

## Trigger

The User wants their data mirrored to a folder another tool can read.

## Outcome

The folder is remembered and the first sync runs (sync-csv-folder).
