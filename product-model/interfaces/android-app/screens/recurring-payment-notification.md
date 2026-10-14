---
entities:
  - { entity: recurring-expense, shows: [Amount, Category, Frequency] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/NotificationHelper.kt#showRecurrentExpenseNotification"
---

# Recurring payment reminder

The notification that a recurring payment is due today or coming up, with Mark as paid and Skip.
