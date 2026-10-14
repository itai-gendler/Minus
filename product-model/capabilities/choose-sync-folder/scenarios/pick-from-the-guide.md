---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User opens CSV folder sync guide in Extra features and picks a folder"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::csv-folder-sync
  - text: "The Product saves the App settings sync folder and syncs now"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Sync folder] }
    contexts:
      app:
        place: android-app::csv-folder-sync
---

# Pick the folder from the sync guide

## Trigger

The User reads how the folder sync works first.

## Outcome

The folder is set from the guide.
