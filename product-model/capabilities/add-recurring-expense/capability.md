---
availability:
  - { place: android-app }
domain: subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#applyRecurrentExpense"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/dialogs/RecurrentExpenseDialog.kt"
---

# Add recurring expense

Turn on Recurrent on Home, type the amount and category and tap Done, then set how often it is charged (Weekly, Biweekly or Monthly), the billing day for a monthly one, and the limit date. Minus charges it on every due date until then and reminds the person before and on each one.
