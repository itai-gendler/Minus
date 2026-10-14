---
appliesTo:
  - type: capability
    id: check-remaining-budget
  - type: capability
    id: browse-subscriptions
  - type: capability
    id: mark-recurring-payment-paid
  - type: capability
    id: skip-recurring-payment
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/HistoryCalculations.kt#splitRecurringAndOneTime"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetStateCalculator.kt#calculateBudgetState"
---

# A recurring charge counts against the budget on its due date unless it is settled

Each charge of a recurring expense that falls inside the period counts as spent on its due date. Marking it paid records an expense in its place, and skipping it removes it. With Reserve upcoming charges on, every charge due later in the period is set aside from the first day, so the allowance shows only what is free to spend.
