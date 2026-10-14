---
kind: edge
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
  - text: "The Product ends the Budget period today with nothing to carry"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: changes, from: "Active", to: "Ended", facts: [Finished early on] }
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

# Finalize with nothing left

## Trigger

Everything was spent or the period was overspent.

## Outcome

The period is finished and nothing waits for the next one.
