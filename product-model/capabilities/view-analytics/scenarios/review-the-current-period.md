---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens Analytics"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::analytics
  - text: "The User reads the Budget period's spending, each Expense and the split by day"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Total budget, Spent, Remaining] }
      - { entity: expense, effect: reads, facts: [Amount, Category, Date] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The User reads the savings recommendation"
    kind: actor
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Savings split, Savings goal] }
    contexts:
      app:
        place: android-app::analytics
---

# Review the current period

## Trigger

The User wants to see how the period is going.

## Outcome

Charts, categories, the heatmap and the savings recommendation describe the active period.

## Edge cases

- Expenses without a category are grouped as Uncategorized.
