---
appliesTo:
  - type: capability
    id: end-budget-period
  - type: capability
    id: finish-budget-period-early
  - type: capability
    id: decide-period-surplus
  - type: capability
    id: create-budget-period
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/time/MidnightPeriodChecker.kt#handleEndingPeriod"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetPeriodManager.kt#persistBudgetSettings"
---

# Money left at the end of a period follows End of period surplus

Ask me asks the person when the period ends; Spread all adds the leftover to the next period's total and spreads it over its days; Day 1 lump adds it to the next period's first day. A period that ends with nothing left, or overspent, carries nothing, and a discarded leftover is gone.
