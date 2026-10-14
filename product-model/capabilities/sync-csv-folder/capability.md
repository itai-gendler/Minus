---
availability:
  - { place: android-app }
domain: settings
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/CsvSyncWorker.kt"
  - kind: doc
    role: intent
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/features/CsvSyncGuideScreen.kt"
    title: "CSV folder sync guide"
---

# Sync CSV folder

Every two hours, right after a folder is picked, and when an outside tool asks Minus to sync now, Minus syncs with the sync folder: it imports every minus_import_*.csv file, then writes minus_synced.csv with everything it keeps, keeping the five previous copies as minus_backup- files.
