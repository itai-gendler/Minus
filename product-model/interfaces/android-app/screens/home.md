---
entities:
  - { entity: budget-period, shows: [Remaining, Pending extra money, Leftover choices] }
  - { entity: expense, collects: [Amount, Kind, Category, Extra note, Paid with credit card] }
  - { entity: category, shows: [Name], collects: [Name] }
  - { entity: recurring-expense, collects: [Frequency, Billing day, Recurrence end] }
  - { entity: credit-card, shows: [Total owed], collects: [Cutoff day] }
  - { entity: app-settings, shows: [Budget view] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/home/MainScreenContent.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/Editor.kt"
---

# Home

The calculator-style numpad where expenses, income and deductions are entered, with the budget pill showing what is left, the category and extra note fields, and the Recurrent and credit card toggles.
