---
appliesTo:
  - type: capability
    id: sync-with-phone
  - type: capability
    id: record-expense
references:
  - kind: code
    role: implementation
    target: "app/src/wear/java/com/serranoie/app/minus/wearsync/WearExpenseIngestor.kt"
  - kind: code
    role: implementation
    target: "wear/src/main/java/com/serranoie/app/wear/minus/data/PendingExpenseStore.kt"
---

# An expense from the watch is recorded once on the phone

Each expense saved on the watch carries its own identity; the phone records it once however many times it arrives, and the watch keeps it until the phone acknowledges it.
