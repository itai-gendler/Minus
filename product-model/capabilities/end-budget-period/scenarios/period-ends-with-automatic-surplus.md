---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The finish date of the active Budget period has passed and End of period surplus is Spread all or Day 1 lump"
    kind: condition
    unattended: true
    entities:
      - { entity: budget-period, effect: reads, facts: [Finish date, End of period surplus] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The Product ends the Budget period and keeps what is left for the next period"
    kind: product
    entities:
      - { entity: budget-period, effect: changes, from: "Active", to: "Ended", facts: [Pending extra money] }
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

# A period ends with an automatic surplus

## Trigger

A period ends while the leftover is set to be spread or added to day one.

## Outcome

No question is asked and the finished period's summary is shown.
