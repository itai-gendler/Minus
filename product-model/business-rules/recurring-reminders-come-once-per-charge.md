---
appliesTo:
  - type: capability
    id: send-recurring-payment-reminder
  - type: capability
    id: mark-recurring-payment-paid
  - type: capability
    id: skip-recurring-payment
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/RecurrentExpenseNotificationWorker.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/NotificationScheduler.kt#nextOccurrenceDateTime"
---

# Each recurring charge is reminded once ahead and once on the day

A recurring charge gets one Upcoming expense reminder three days before and one reminder on its due date, at the Recurring payments time. A charge already marked paid or skipped, a charge after the recurrence end and a deleted recurring expense get none.
