---
appliesTo:
  - type: capability
    id: create-budget-period
  - type: capability
    id: edit-budget-period
  - type: capability
    id: browse-past-periods
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetPeriodManager.kt#persistBudgetSettings"
---

# Starting a new period turns the ended one into a past period; editing keeps the period

Applying a budget after the active period has ended or was finalized starts a new period and keeps the previous one among the past periods with what it spent. Applying changes while the period is still running edits that same period, which keeps its expenses.
