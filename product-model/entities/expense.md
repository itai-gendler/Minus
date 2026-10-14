---
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/TransactionModel.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/local/entity/QueuedTransactionEntity.kt"
  - kind: code
    role: implementation
    target: "wear/src/main/java/com/serranoie/app/wear/minus/data/PendingExpense.kt"
---

# Expense

One amount recorded against the budget: money spent, income added, or a deduction from the budget.

## Information kept

- **Amount** — the amount, in the period's currency
- **Kind** — Expense, Income added or Deducted budget
- **Category** — the category name it was saved with, or none
- **Extra note** — an optional note, such as what exactly was bought or the app a spend reminder came from
- **Date** — the day and time it happened
- **Paid with credit card** — whether it was paid with the credit card
- **Credit paid** — for a credit card expense, whether the card has been paid for it

## States

### Recorded

Counted in its budget period.

### Queued for next period

Recorded after the active period's finish date; it joins the next period when that one starts.

### Waiting for phone

Saved on the watch and not yet received by the phone.
