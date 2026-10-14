---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User asks to delete an Expense in a past Budget period's breakdown"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Start date] }
      - { entity: expense, effect: reads, facts: [Amount] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The User confirms and unlocks with a fingerprint"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::analytics
  - text: "The Product deletes the Expense"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: removes, from: "Recorded" }
    contexts:
      app:
        place: android-app::analytics
---

# Delete an expense of a past period

## Trigger

An expense in a closed period should not be there.

## Outcome

The expense is gone and the past period's figures follow.
