---
availability:
  - { place: android-app }
domain: subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#markRecurrentOccurrencePaid"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/RecurrentNotificationActionReceiver.kt"
---

# Mark recurring payment paid

Confirm a due or past charge of a recurring expense with Mark as paid, from Subscriptions, the history or the reminder notification. Minus records an expense for it today in the active period.
