---
availability:
  - { place: wear-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "wear/src/main/java/com/serranoie/app/wear/minus/sync/WearSyncRepository.kt"
  - kind: code
    role: implementation
    target: "wear/src/main/java/com/serranoie/app/wear/minus/sync/WearSyncScheduler.kt"
  - kind: code
    role: implementation
    target: "app/src/wear/java/com/serranoie/app/minus/wearsync/WearExpenseIngestor.kt"
  - kind: code
    role: implementation
    target: "app/src/wear/java/com/serranoie/app/minus/wearsync/WearBudgetStateProvider.kt"
---

# Sync with phone

The watch sends the expenses waiting on it to the paired phone, which records each one in its active budget period, and gets back the current budget and the latest category names. It syncs when an expense is saved, when the watch app opens, every 15 minutes, and when the person taps Sync now.
