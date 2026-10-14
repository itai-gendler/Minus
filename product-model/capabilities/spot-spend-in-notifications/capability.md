---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/scan/ExpenseNotificationListener.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/notification/ExpenseNotificationParser.kt"
---

# Spot spend in notifications

While Spend reminders is on and notification access is granted, Minus reads new notifications of the apps chosen to watch, on the phone only, and when one carries an amount in the budget's currency it posts a spend reminder: "Seems like you just spent ... Don't forget to minus it." Nothing is recorded until the person saves it.
