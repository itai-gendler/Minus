---
entities:
  - { entity: app-settings, shows: [Period end time, Recurring payments time, Savings split, Savings goal, Sync folder, Last sync, Privacy mode], collects: [Period end time, Recurring payments time, Savings split, Savings goal] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/Settings.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/SettingsViewModel.kt"
---

# Settings

The settings page: notifications, savings preferences, data backup and sync, privacy mode, widgets, and links to theming, extra features and app information.
