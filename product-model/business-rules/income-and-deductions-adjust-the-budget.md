---
appliesTo:
  - type: capability
    id: add-income
  - type: capability
    id: deduct-from-budget
  - type: capability
    id: check-remaining-budget
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetStateCalculator.kt#calculateBudgetState"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#applyTransaction"
---

# Income raises the budget and deductions lower it without counting as spending

An amount entered with a leading + is Income added: it raises the period's budget and today's allowance. An amount entered with a leading - is Deducted budget: it lowers the period's budget. Neither counts toward what was spent.
