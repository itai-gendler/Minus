---
entities:
  - { entity: budget-period, shows: [Remaining, Spent, Total budget, Finish date] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/widget/BudgetPillWidget.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/widget/CompleteBudgetWidget.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/tile/NewTransactionTileService.kt"
---

# Home-screen widgets

The Minus widgets and the Quick Settings tile outside the app: the budget pill, budget overview, days countdown, average and minimum or maximum spent, spending heatmaps, and the add expense shortcuts.
