---
availability:
  - { place: android-app }
domain: subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#editTransaction"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/edit/RecurrenceConfigSheet.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/subscriptions/SubscriptionsViewModel.kt#onSaveEdited"
---

# Edit recurring expense

Change a recurring expense from Subscriptions or the history: its amount, category, frequency, billing day, recurrence end or credit card mark. Turning recurrence off makes it a one-time expense.
