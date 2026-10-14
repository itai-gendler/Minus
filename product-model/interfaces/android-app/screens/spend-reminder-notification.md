---
entities:
  - { entity: expense, shows: [Amount] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/NotificationHelper.kt#showSpendDetectedNotification"
---

# Spend reminder

The notification that a charge was spotted in another app, with Minus it and Save as is, and, once saved, Undo.
