---
availability:
  - { place: android-app }
domain: budget
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/time/MidnightPeriodChecker.kt#resolveUnresolvedSurplus"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/MainActivity.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/component/RolloverDialog.kt"
---

# Decide period surplus

When a period ends with money left and End of period surplus is Ask me, choose what to do with it: Split equally across the next budget's days, Add to today (the next budget's first day), or Discard remaining budget. The question can be dismissed; a Pending extra money banner on Home reopens it.
