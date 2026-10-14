---
kind: primary
result: achieved
routes:
  app: Android app
steps:
  - text: "The User taps Finalize budget period early and confirms"
    kind: actor
    capability: finish-budget-period-early
    actor: user
    entities:
      - { entity: budget-period, as: previous, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product ends the Budget period and opens its analytics"
    kind: product
    capability: finish-budget-period-early
    actor: user
    entities:
      - { entity: budget-period, as: previous, effect: changes, from: "Active", to: "Ended", facts: [Finished early on, Pending extra money] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The User taps New budget and applies the next period's budget"
    kind: actor
    capability: create-budget-period
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product closes the ended Budget period and starts the new one"
    kind: product
    capability: create-budget-period
    actor: user
    entities:
      - { entity: budget-period, as: previous, effect: changes, from: "Ended", to: "Past", facts: [Spent] }
      - { entity: budget-period, as: next, effect: creates, to: "Active", facts: [Total budget, Start date, Finish date, Currency, End of period surplus, Daily amount, Carried in, Leftover choices, Finished early on, Spent, Pending extra money, Remaining] }
    contexts:
      app:
        place: android-app::budget-period
---

# After finishing a period early

## Trigger

The User finalizes the active period before its finish date.

## Outcome

The finished period's analytics led into the new period's setup, and the new period is active.
