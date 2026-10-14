---
availability:
  - { place: android-app }
domain: settings
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/csv/CsvTransferManager.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/MinusCsvExporter.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/csv/MinusCsvService.kt#exportAllTransactions"
---

# Export CSV

Back up data writes everything Minus keeps into one CSV file in Downloads and offers to share it: every expense and recurring expense, the past periods, and the active period's settings.
