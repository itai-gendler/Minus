---
singleton: true
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/CreditCard.kt"
---

# Credit card

The person's credit card, kept to tell what they owe on it and when to pay.

## Information kept

- **Cutoff day** — the billing cutoff day of the month, 1 to 31
- **Payment due date** — the date the payment for the last cutoff is due
- **Total owed** — the credit card expenses not yet marked as paid
