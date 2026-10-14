---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/scan/ExpenseScanActionReceiver.kt#quickSave"
---

# Quick-save spotted spend

Tap Save as is on a spend reminder to record the spotted amount at once, without a category and with the app's name as the extra note; the notification then offers Undo (delete-expense).
