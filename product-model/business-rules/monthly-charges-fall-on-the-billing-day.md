---
appliesTo:
  - type: capability
    id: add-recurring-expense
  - type: capability
    id: send-recurring-payment-reminder
  - type: capability
    id: browse-subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/NotificationScheduler.kt#nextMonthlyOccurrence"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/subscriptions/SubscriptionsViewModel.kt"
---

# A monthly charge falls on its billing day, or the month's last day

A monthly recurring expense is charged on its billing day each month; in a month without that day it is charged on the month's last day. Weekly and biweekly ones are charged every seven or fourteen days from their first charge.
