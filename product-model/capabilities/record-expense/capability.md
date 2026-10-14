---
availability:
  - { place: android-app }
  - { place: wear-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#applyTransaction"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/controller/NumpadController.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/Editor.kt"
  - kind: doc
    role: intent
    target: "README.md"
    title: "README features"
---

# Record expense

Type an amount on the numpad, optionally a category, an extra note and the credit card mark, and tap Done to record an expense in the active budget period. The numpad also calculates: swipe up for the operators and the result is what gets saved. On the watch the expense is typed on the watch numpad and handed to the phone.
