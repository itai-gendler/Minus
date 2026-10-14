---
entities:
  - { entity: budget-period, shows: [Total budget, Spent, Start date, Finish date, Remaining, Finished early on] }
  - { entity: expense, shows: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid], collects: [Amount, Category, Extra note, Date, Paid with credit card] }
  - { entity: credit-card, shows: [Cutoff day, Payment due date, Total owed], collects: [Cutoff day] }
  - { entity: app-settings, shows: [Savings split, Savings goal] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/Analytics.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/AnalyticsViewModel.kt"
---

# Analytics

The spending of the current, just finished or a chosen past period: the spending trend against the previous period, categories, a daily heatmap, minimum, maximum and average spent, the savings recommendation, the credit card section and, for a finished period, its summary with a New budget button.
