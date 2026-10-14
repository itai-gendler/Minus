---
availability:
  - { place: android-app }
domain: subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/subscriptions/SubscriptionsViewModel.kt#onSkip"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/RecurrentNotificationActionReceiver.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/AnalyticsViewModel.kt#deleteTransaction"
---

# Skip recurring payment

Skip one charge of a recurring expense (Skip on this period) from Subscriptions or the reminder notification; it is not charged against the budget. Deleting a past period's recurring charge from its breakdown also skips it.
