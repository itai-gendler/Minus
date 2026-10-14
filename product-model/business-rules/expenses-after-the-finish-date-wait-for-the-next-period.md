---
appliesTo:
  - type: capability
    id: record-expense
  - type: capability
    id: quick-save-spotted-spend
  - type: capability
    id: create-budget-period
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetTransactionHandler.kt#applyTransaction"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/repository/BudgetRepositoryImpl.kt#assignQueuedTransactionsToPeriod"
---

# An expense recorded after the finish date waits for the next period

Once the active period's finish date has passed and no new period has started, an expense recorded on Home or saved from a spend reminder is kept apart and moved into the next period when it starts.
