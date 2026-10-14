---
entities:
  - { entity: expense, shows: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid], collects: [Amount, Category, Extra note, Date, Paid with credit card] }
  - { entity: recurring-expense, shows: [Amount, Category, Frequency, Billing day, Recurrence end], collects: [Amount, Category, Frequency, Billing day, Recurrence end, Paid with credit card] }
  - { entity: recurring-payment, shows: [Due date] }
  - { entity: credit-card, shows: [Total owed], collects: [Cutoff day] }
  - { entity: budget-period, shows: [Remaining] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/HistoryScreen.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/edit/TransactionEditScreen.kt"
---

# Expenses history

The list of the period's expenses grouped by date, the recurring payments of this period and the upcoming ones, the credit owed, and the editor for one expense.
