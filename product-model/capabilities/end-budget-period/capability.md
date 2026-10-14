---
availability:
  - { place: android-app }
domain: budget
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/time/MidnightPeriodChecker.kt#handleEndingPeriod"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/notification/MidnightPeriodTransitionReceiver.kt"
  - kind: doc
    role: context
    target: "PROJECT_OVERVIEW.md"
    title: "Midnight alarm receiver"
---

# End budget period

At midnight after the finish date, and whenever the app starts, Minus checks whether the active period is over. An ended period notifies the person, and the next time the app is open it either asks what to do with the money left (End of period surplus Ask me) or keeps it for the next period and opens the finished period's analytics.
