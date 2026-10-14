---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens Past periods"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::past-periods
  - text: "The User reads each past Budget period's dates, limit and spending"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Start date, Finish date, Total budget, Spent] }
    contexts:
      app:
        place: android-app::past-periods
---

# List past periods

## Trigger

The User wants to look back over earlier periods.

## Outcome

Every past period is listed, newest first, with On Track, Over Budget or Saved.

## Edge cases

- With no past periods, No archived periods found is shown.
