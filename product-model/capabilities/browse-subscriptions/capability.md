---
availability:
  - { place: android-app }
domain: subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/subscriptions/SubscriptionsViewModel.kt#buildUiState"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/calculator/RecurringExpenseCalculator.kt"
---

# Browse subscriptions

Open Subscriptions from Analytics to see every active recurring expense: the monthly commitment and active count, what is due today and in the next seven days, what comes later, the period's charges by day with their Paid, Skipped or pending status, and the split by billing frequency and category.
