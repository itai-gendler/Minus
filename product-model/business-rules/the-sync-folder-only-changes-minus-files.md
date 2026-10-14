---
appliesTo:
  - type: capability
    id: sync-csv-folder
  - type: capability
    id: choose-sync-folder
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/CsvSyncWorker.kt"
---

# Folder sync touches only its own files

In the sync folder Minus reads only files named minus_import_*.csv, renames each to .imported or .rejected once read, writes minus_synced.csv, and keeps the five most recent minus_backup- copies; it deletes nothing else. Each sync imports before it exports, and a folder copy is restored, never overwritten, into a Minus that keeps no data.
