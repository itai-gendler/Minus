---
appliesTo:
  - type: capability
    id: create-budget-period
  - type: capability
    id: edit-budget-period
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/sheets/BudgetPeriodSheet.kt"
---

# A budget period needs a total above zero and at least one day

The budget editor applies only a total budget greater than zero with a finish date on or after the start date.
