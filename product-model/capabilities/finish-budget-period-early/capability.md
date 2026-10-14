---
availability:
  - { place: android-app }
domain: budget
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetPeriodManager.kt#finishBudgetEarly"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/time/MidnightPeriodChecker.kt#handleEarlyFinish"
---

# Finish budget period early

Finalize budget period early from the budget sheet: after confirming, the active period ends today, what is left is settled by its End of period surplus, and Minus opens the period's analytics.
