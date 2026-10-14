---
availability:
  - { place: android-app }
domain: settings
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/BudgetPeriodManager.kt#updateRecurrentNotificationTime"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/SettingsViewModel.kt#onNotificationTimeChange"
---

# Change notification settings

In the Notifications section of Settings, pick the Period end time and the Recurring payments time; scheduled reminders move to the new times. The section also shows whether notifications and exact alarms are allowed, with a shortcut to Android's settings.
