---
availability:
  - { place: android-app }
domain: budget
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/NotificationScheduler.kt#schedulePeriodEndNotification"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/PeriodEndAlarmReceiver.kt"
---

# Remind period end

Once a period's finish date has passed, Minus posts a Budget period finished notification at the chosen Period end time, saying what was left or how much extra was spent; tapping it opens the app.
