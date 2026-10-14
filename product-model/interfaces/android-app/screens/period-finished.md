---
entities:
  - { entity: budget-period, shows: [Start date, Finish date, Spent, Pending extra money] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/component/RolloverDialog.kt"
---

# Period finished

The question asked when a period ends with money left and End of period surplus is Ask me: split it equally, add it to today, or discard it. It is also reached again from the Pending extra money banner on Home.
