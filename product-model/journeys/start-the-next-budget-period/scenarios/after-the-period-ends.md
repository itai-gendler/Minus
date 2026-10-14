---
kind: alternative
result: achieved
routes:
  app: Android app
steps:
  - text: "The User chooses Split equally on the Period finished question"
    kind: actor
    capability: decide-period-surplus
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::period-finished
  - text: "The Product keeps the money for the next Budget period and opens the finished period's analytics"
    kind: product
    capability: decide-period-surplus
    actor: user
    entities:
      - { entity: budget-period, as: previous, effect: changes, facts: [Pending extra money] }
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
  - text: "The Product closes the ended Budget period and starts the new one with the money spread over it"
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

# After a period ends with money left

## Trigger

The period passed its finish date with money left and End of period surplus is Ask me.

## Outcome

The leftover was decided, the summary led into the new period's setup, and the new period is active.
