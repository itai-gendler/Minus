---
availability:
  - { place: android-app }
domain: budget
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetStateCalculator.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetViewModel.kt#onLeftoverChoice"
---

# Choose daily leftover

With Daily amount set to Your call each day, decide each day what happens to yesterday's unused budget: Spread over the days left, or Add it all to today. Overspending is always spread over the days left.
