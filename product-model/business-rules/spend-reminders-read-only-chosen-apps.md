---
appliesTo:
  - type: capability
    id: spot-spend-in-notifications
  - type: capability
    id: change-spend-reminder-settings
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/notification/ExpenseNotificationParser.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/scan/ExpenseNotificationListener.kt"
---

# Spend reminders read only the chosen apps' new notifications, on the phone

Only notifications posted by the apps chosen to watch, after reading started, are read, and only on the phone; a reminder is posted only for an amount next to the budget currency's code, or its symbol when no other supported currency shares it. Refunds, deposits, balances, cashback, codes, discounts and promotions, and amounts after a +, are ignored. Nothing is kept until the person saves it.
