---
availability:
  - { place: android-app }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/NotificationScheduler.kt#scheduleCreditCutoffReminder"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/RecurrentExpenseNotificationWorker.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/CreditCard.kt#calculatePaymentDueDate"
---

# Send credit card reminder

Three days before the credit card payment due date, at the Recurring payments time, Minus says when the payment is due and how much to pay to avoid interest: the credit card expenses up to the last cutoff that are not marked paid.
