---
domain: subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/local/entity/PaidRecurrentOccurrenceEntity.kt"
---

# Recurring payment

One due charge of a recurring expense that the person settled, by marking it paid or skipping it.

## Information kept

- **Due date** — the day this charge was due

## States

### Paid

Marked as paid: an expense was recorded for it.

### Skipped

Skipped for this period: nothing is charged for it.
