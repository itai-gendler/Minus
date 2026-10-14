---
availability:
  - { place: android-app }
domain: settings
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/SettingsViewModel.kt#onSyncFolderResult"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/features/CsvSyncGuideScreen.kt"
---

# Choose sync folder

Pick a folder in Settings to keep a CSV copy of Minus in; Minus syncs with it right away and then about every two hours.
