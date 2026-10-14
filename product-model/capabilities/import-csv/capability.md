---
availability:
  - { place: android-app }
domain: settings
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/MinusCsvService.kt#importTransactions"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/MinusCsvParser.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/CsvImportWorker.kt"
---

# Import CSV

Import CSV reads a Minus CSV file in the background: it adds or replaces expenses, adds past periods, and, when the file carries the active period's settings, restores them.
