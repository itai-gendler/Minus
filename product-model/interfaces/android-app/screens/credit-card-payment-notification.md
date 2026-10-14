---
entities:
  - { entity: credit-card, shows: [Payment due date, Total owed] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/NotificationHelper.kt#showCreditCutoffNotification"
---

# Credit card payment reminder

The notification of the coming credit card payment due date and the amount to pay to avoid interest.
