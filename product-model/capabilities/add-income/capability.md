---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#applyTransaction"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetViewModel.kt"
---

# Add income

Type a leading + before the amount to add money to the budget instead of spending it; the budget pill previews "will be added" before Done.
