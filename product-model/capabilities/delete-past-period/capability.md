---
availability:
  - { place: android-app }
domain: analytics
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/repository/BudgetRepositoryImpl.kt#deleteArchivedBudget"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/Analytics.kt"
---

# Delete past period

Long-press a past period and confirm, then unlock with biometrics, to delete it permanently with its one-time expenses. Recurring expenses are kept.
