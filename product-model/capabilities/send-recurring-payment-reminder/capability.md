---
availability:
  - { place: android-app }
domain: subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/NotificationScheduler.kt#scheduleRecurrentExpenseNotification"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/RecurrentExpenseNotificationWorker.kt"
---

# Send recurring payment reminder

Minus reminds the person of each charge of a recurring expense: three days before (Upcoming expense) and on the due date (Your payment is due today, with Mark as paid and Skip), at the Recurring payments time.
