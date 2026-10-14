---
kind: alternative
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
  - text: "The Product ends the Budget period today and keeps what is left for the next period by its End of period surplus"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: changes, from: "Active", to: "Ended", facts: [Finished early on, Pending extra money] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product opens the finished period's analytics"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Spent] }
    contexts:
      app:
        place: android-app::analytics
---

# Finalize with an automatic surplus

## Trigger

End of period surplus is Spread all or Day 1 lump.

## Outcome

No question is asked; the leftover waits to join the next period as set.
