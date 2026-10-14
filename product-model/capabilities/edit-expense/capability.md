---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#editTransaction"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/edit/TransactionEditScreen.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/Analytics.kt"
---

# Edit expense

Open an expense from the history and change its amount, category, extra note, date, time or credit card mark, or make it recurrent. An expense of a past period is edited from that period's analytics after confirming and unlocking with biometrics.
