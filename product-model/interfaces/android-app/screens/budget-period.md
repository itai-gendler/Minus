---
entities:
  - { entity: budget-period, shows: [Total budget, Spent, Remaining, Start date, Finish date, Currency, End of period surplus, Daily amount, Carried in], collects: [Total budget, Start date, Finish date, Currency, End of period surplus, Daily amount] }
  - { entity: expense, shows: [Amount] }
  - { entity: app-settings, shows: [Budget view], collects: [Budget view] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/sheets/BudgetPeriodSheet.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/sheets/BudgetBehaviourContent.kt"
---

# Budget period

The budget sheet opened from the budget pill: the total budget, spent and available amounts, the dates, the per-view breakdown and how it is calculated, and the editor for a new or changed budget period with its currency and budget behavior.
