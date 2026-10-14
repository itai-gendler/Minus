---
entities:
  - { entity: recurring-expense, shows: [Amount, Category, Frequency, Billing day, First charge, Recurrence end], collects: [Amount, Category, Frequency, Billing day, Recurrence end, Paid with credit card] }
  - { entity: recurring-payment, shows: [Due date] }
  - { entity: budget-period, shows: [Total budget, Start date, Finish date] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/subscriptions/SubscriptionsScreen.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/subscriptions/SubscriptionsViewModel.kt"
---

# Subscriptions

Every active recurring expense: the monthly commitment, what is due soon and upcoming, the period's charges by day with their paid, skipped or pending status, and the split by billing frequency and category.
