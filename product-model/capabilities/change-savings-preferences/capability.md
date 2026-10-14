---
availability:
  - { place: android-app }
domain: settings
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/savings/SavingsPreferencesEditor.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/SavingsPreferences.kt"
---

# Change savings preferences

In Savings preferences, choose the needs, wants and savings split (Balanced 50/30/20, Aggressive saver 40/20/40, Conservative 70/20/10, or a Custom split that adds up to 100%) and an optional savings goal with a target amount and months. The savings recommendation in Analytics follows them.
