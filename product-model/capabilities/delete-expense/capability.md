---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#deleteTransaction"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/HistoryViewModel.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/scan/ExpenseScanActionReceiver.kt"
---

# Delete expense

Swipe an expense away in the history, delete one from a past period's breakdown, or tap Undo on a spend reminder that saved it. Deleting from Home and the history offers UNDO for a few seconds (restore-deleted-expense).
