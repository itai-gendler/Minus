---
domain: subscriptions
relations:
  - entity: recurring-payment
    verb: has
    cardinality: one-to-many
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/TransactionModel.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/calculator/RecurringExpenseCalculator.kt"
---

# Recurring expense

An expense or subscription charged again and again until its recurrence end; the Subscriptions screen lists every one.

## Information kept

- **Amount** — what each charge costs
- **Category** — the category name, also used as its name
- **Frequency** — Weekly, Biweekly or Monthly
- **Billing day** — for a monthly one, the day of the month it is charged
- **First charge** — the date of its first charge
- **Recurrence end** — the last day it can be charged
- **Paid with credit card** — whether it is charged to the credit card
