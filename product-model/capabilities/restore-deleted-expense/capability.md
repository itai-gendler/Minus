---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#restoreTransaction"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/home/MainScreenViewModel.kt"
---

# Restore deleted expense

Tap UNDO on the snackbar shown after deleting an expense to bring it back.
