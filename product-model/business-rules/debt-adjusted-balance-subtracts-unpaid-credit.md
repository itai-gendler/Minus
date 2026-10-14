---
appliesTo:
  - type: capability
    id: browse-expense-history
  - type: capability
    id: mark-credit-expense-paid
  - type: entity
    id: credit-card
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetViewModel.kt"
---

# The debt-adjusted balance is what is left minus unpaid credit

The total owed is every credit card expense not marked as paid, and the debt-adjusted balance is what is left today minus that total.
