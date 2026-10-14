---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User opens a past Budget period's breakdown and taps one of its Expense entries"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Start date] }
      - { entity: expense, effect: reads, facts: [Amount] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The User confirms the change and unlocks with a fingerprint"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::analytics
  - text: "The User changes its values and saves them"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::analytics
  - text: "The Product saves the changed Expense in its past period"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: changes, facts: [Amount, Category, Extra note, Date, Paid with credit card] }
    contexts:
      app:
        place: android-app::analytics
---

# Edit an expense of a past period

## Trigger

An expense in a closed period needs correcting.

## Outcome

The expense is changed and the past period's figures follow; further changes stay unlocked while the breakdown is open.
