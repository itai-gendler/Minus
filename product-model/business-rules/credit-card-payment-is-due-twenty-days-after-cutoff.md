---
appliesTo:
  - type: capability
    id: send-credit-card-reminder
  - type: capability
    id: set-credit-cutoff-day
  - type: entity
    id: credit-card
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/CreditCard.kt#calculatePaymentDueDate"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/RecurrentExpenseNotificationWorker.kt"
---

# The credit card payment is due twenty days after the last cutoff

The payment due date is twenty days after the most recent cutoff day, moved to the following Monday when it falls on a weekend. The amount to pay is every credit card expense up to that cutoff not marked as paid, and it is reminded once, three days before the due date.
