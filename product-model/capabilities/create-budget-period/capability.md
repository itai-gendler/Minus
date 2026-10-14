---
availability:
  - { place: android-app }
domain: budget
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetPeriodManager.kt#persistBudgetSettings"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/sheets/BudgetPeriodSheet.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/repository/BudgetRepositoryImpl.kt#assignQueuedTransactionsToPeriod"
---

# Create budget period

Set up a new budget period on the budget sheet: the total budget, the start and finish dates, the base currency, and the budget behavior (End of period surplus and Daily amount). Minus requires it after the welcome and again whenever the previous period has ended; starting it closes the previous period as a past period, adds any surplus decided for it, and moves the expenses waiting for the next period into it.
