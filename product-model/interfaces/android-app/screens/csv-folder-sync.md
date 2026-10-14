---
entities:
  - { entity: app-settings, shows: [Sync folder, Last sync], collects: [Sync folder] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/features/CsvSyncGuideScreen.kt"
---

# CSV folder sync

The sync folder, the last sync status, and the guide to the files Minus reads and writes there.
