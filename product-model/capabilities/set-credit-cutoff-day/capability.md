---
availability:
  - { place: android-app }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetViewModel.kt#handleCreditCutoffDayConfirmed"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/AnalyticsViewModel.kt#onCutoffDayChanged"
---

# Set credit cutoff day

Set the credit card's billing cutoff day (1 to 31), which decides when the payment is due and when the reminder comes. It is asked the first time an expense is marked as paid with the credit card, and can be changed in the credit card section of Analytics and when editing an expense.
