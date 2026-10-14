---
domain: budget
relations:
  - entity: expense
    verb: holds
    cardinality: one-to-many
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/BudgetPeriodModel.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/ArchivedBudget.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetPeriodManager.kt"
---

# Budget period

One budget from a start date to a finish date: the money there is to spend, how it is spread over the days, and what happens to what is left. One period is active at a time; earlier ones are kept as past periods.

## Information kept

- **Total budget** — the amount to spend from the start date to the finish date, including any surplus carried in
- **Start date** — the first day of the period
- **Finish date** — the last day of the period
- **Currency** — the base currency every amount of the period is shown in
- **End of period surplus** — Ask me, Spread all or Day 1 lump: what happens to money left when the period ends
- **Daily amount** — Same every day, Rebalanced daily, Saved for later or Your call each day: how the budget is spread over the days
- **Carried in** — surplus from the previous period added to this one, and whether it is spread or added to the first day
- **Leftover choices** — under Your call each day, the choice made each day to spread yesterday's unused budget or add it to today
- **Finished early on** — when the period was finalized before its finish date
- **Spent** — what was spent in the period, recurring charges included
- **Pending extra money** — money left from an ended period that still waits for a decision or for the next period
- **Remaining** — what is left to spend today, this week, these two weeks or this month, by the chosen Budget view

## States

### Active

The current period: expenses go into it and its allowance is shown.

### Ended

Its finish date has passed, or it was finalized early; what is left is settled and a new period is due.

### Past

A closed period kept among the past periods with what was spent; it can be opened or deleted.
