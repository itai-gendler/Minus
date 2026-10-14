---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#applyTransaction"
---

# Deduct from budget

Type a leading - before the amount to lower the budget without counting it as spending; the budget pill previews "will be subtracted" before Done.
