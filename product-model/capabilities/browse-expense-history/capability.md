---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/HistoryViewModel.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/HistoryCalculations.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/sections/TransactionDateSections.kt"
---

# Browse expense history

Swipe up from Home to the expenses history: the period's expenses grouped by date with daily totals, the recurring payments of this period and the upcoming ones, and, with credit card payments on, the total owed and the debt-adjusted balance. Past periods' expenses load on request when Show past transactions is on.
