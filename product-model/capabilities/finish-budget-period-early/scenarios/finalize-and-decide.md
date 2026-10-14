---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User taps Finalize budget period early and confirms Finalize"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product ends the Budget period today and keeps what is left as pending extra money"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: changes, from: "Active", to: "Ended", facts: [Finished early on, Pending extra money] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product opens the finished period's analytics and asks what to do with the remaining money"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Pending extra money] }
    contexts:
      app:
        place: android-app::period-finished
---

# Finalize with money left

## Trigger

The User wants to close the period before its finish date, with End of period surplus set to Ask me.

## Outcome

The period is finished and the Period finished question is shown (decide-period-surplus).
