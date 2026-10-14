---
kind: edge
routes:
  app: Android app
steps:
  - text: "The finish date of the active Budget period has passed with nothing left"
    kind: condition
    unattended: true
    entities:
      - { entity: budget-period, effect: reads, facts: [Finish date, Spent] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The Product ends the Budget period with nothing to carry"
    kind: product
    entities:
      - { entity: budget-period, effect: changes, from: "Active", to: "Ended", facts: [] }
    contexts:
      app:
        place: android-app::analytics
  - text: "When the app is next open, the Product shows the finished period's analytics"
    kind: product
    entities:
      - { entity: budget-period, effect: reads, facts: [Spent] }
    contexts:
      app:
        place: android-app::analytics
---

# A period ends with nothing left

## Trigger

Everything was spent, or more.

## Outcome

The summary says the budget was exceeded, and a new period is due.
