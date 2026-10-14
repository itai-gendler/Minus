---
availability:
  - { place: android-app }
domain: subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#deleteTransaction"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/dialogs/DeleteRecurrentExpenseDialog.kt"
---

# Delete recurring expense

Delete a recurring expense from Subscriptions or the history after confirming. Its whole configuration and settled payments go, and no more reminders come; expenses already recorded by marking payments paid stay.
