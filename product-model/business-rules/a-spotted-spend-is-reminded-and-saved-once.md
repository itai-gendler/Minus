---
appliesTo:
  - type: capability
    id: spot-spend-in-notifications
  - type: capability
    id: quick-save-spotted-spend
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/scan/ExpenseNotificationListener.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/scan/ExpenseScanActionReceiver.kt"
---

# A spotted charge is reminded once and saved once

The same amount from the same app within a minute gets one spend reminder, no more than ten reminders are posted in an hour, and Save as is records one expense per reminder however often it is tapped.
