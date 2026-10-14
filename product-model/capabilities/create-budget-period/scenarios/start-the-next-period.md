---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User taps New budget on the finished period's analytics"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, as: previous, effect: reads, facts: [Spent] }
    contexts:
      app:
        place: android-app::analytics
  - text: "The User enters the new total, dates, currency and behavior, starting from the previous values, and taps Apply"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product closes the ended Budget period as a past period with what was spent"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, as: previous, effect: changes, from: "Ended", to: "Past", facts: [Spent] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product starts the new Budget period with any surplus carried in"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, as: next, effect: creates, to: "Active", facts: [Total budget, Start date, Finish date, Currency, End of period surplus, Daily amount, Carried in, Leftover choices, Finished early on, Spent, Pending extra money, Remaining] }
      - { entity: budget-period, as: previous, effect: reads, facts: [Pending extra money] }
    contexts:
      app:
        place: android-app::budget-period
  - text: "The Product moves every Expense queued for the next period into it"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: changes, from: "Queued for next period", to: "Recorded", facts: [] }
    contexts:
      app:
        place: android-app::budget-period
---

# Start the next budget period

## Trigger

The previous period has ended or was finalized early.

## Outcome

The previous period is listed among the past periods, the new one is active with its carried-in surplus, and the queued expenses count against it.

## Decision points

### Is surplus waiting for the new period?

What was decided for the previous period's leftover?

- Split equally (Spread all) → the surplus is added to the new total budget and spread over its days.
- Add to today (Day 1 lump) → the surplus is added to the new total budget and to its first day only.
- Discarded, overspent or nothing left → the new period starts with the total entered.
