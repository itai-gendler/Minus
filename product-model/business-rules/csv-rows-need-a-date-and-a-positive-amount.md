---
appliesTo:
  - type: capability
    id: import-csv
  - type: capability
    id: sync-csv-folder
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/MinusCsvParser.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/MinusCsvService.kt#importTransactions"
  - kind: doc
    role: intent
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/features/CsvSyncGuideScreen.kt"
    title: "CSV folder sync guide"
---

# An imported row needs a date and an amount above zero

Each CSV row must have a date in the form yyyy-MM-dd HH:mm and an amount greater than zero; any other row is rejected on its own and the rest of the file is still imported. A row with an id replaces the expense holding that id, and a row without one is added as new without checking for duplicates.
