---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User long-presses a past Budget period and confirms Delete Past Period"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Start date, Finish date] }
    contexts:
      app:
        place: android-app::past-periods
  - text: "The User unlocks with a fingerprint"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::past-periods
  - text: "The Product deletes the Budget period with every one-time Expense it held"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: removes, from: "Past" }
      - { entity: expense, effect: removes, from: "Recorded", with: budget-period }
    contexts:
      app:
        place: android-app::past-periods
---

# Delete a past period

## Trigger

A past period is no longer wanted.

## Outcome

The period and its one-time expenses are gone; recurring expenses and their payments stay.
