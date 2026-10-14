---
kind: edge
routes:
  app: Android app
steps:
  - text: "Minus can no longer reach the Sync folder"
    kind: condition
    unattended: true
    entities:
      - { entity: app-settings, effect: reads, facts: [Sync folder] }
    contexts:
      app:
        place: android-app::csv-folder-sync
  - text: "The Product forgets the Sync folder and records that access was revoked"
    kind: product
    entities:
      - { entity: app-settings, effect: changes, facts: [Sync folder, Last sync] }
    contexts:
      app:
        place: android-app::csv-folder-sync
---

# Folder access was revoked

## Trigger

Android withdrew the folder permission.

## Outcome

The status asks to pick the folder again and no sync runs until then.
