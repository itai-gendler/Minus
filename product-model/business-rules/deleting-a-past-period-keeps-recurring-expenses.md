---
appliesTo:
  - type: capability
    id: delete-past-period
  - type: capability
    id: browse-subscriptions
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/local/dao/TransactionDao.kt#deleteOneTimeByPeriodId"
---

# Deleting a past period deletes its one-time expenses only

A deleted past period takes its one-time expenses with it; recurring expenses and their settled payments are kept.
