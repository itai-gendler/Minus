---
appliesTo:
  - type: capability
    id: check-remaining-budget
  - type: capability
    id: choose-daily-leftover
  - type: entity
    id: budget-period
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetStateCalculator.kt#calculateBudgetState"
  - kind: doc
    role: intent
    target: "README.md"
    title: "Smart Budget Periods"
---

# The allowance follows the period's Daily amount

Same every day divides the total budget equally over every day of the period whatever is spent. Rebalanced daily spreads what is left over the days left, so it moves as the person spends. Saved for later gives each day its equal share and adds whatever a day leaves unspent to the next. Your call each day lets the person choose each day to spread yesterday's leftover or add it to today, while overspending is always spread over the days left. The weekly, biweekly and monthly views add up the days of the current seven, fourteen or thirty day block counted from the start date.
