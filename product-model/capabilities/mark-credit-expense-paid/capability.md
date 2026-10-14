---
availability:
  - { place: android-app }
domain: analytics
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/AnalyticsViewModel.kt#onMarkCreditPaid"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/component/budget/CreditTransactionsBottomSheet.kt"
---

# Mark credit expense paid

While credit card expenses are owed, the credit card section of Analytics lists them: mark one as paid, or Mark all as paid, once the card has been paid; it no longer counts as owed.
