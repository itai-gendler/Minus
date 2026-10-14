---
kind: alternative
routes:
  app: Android app
steps:
  - text: "Show past transactions is on in Extra features"
    kind: condition
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Show past transactions] }
    contexts:
      app:
        place: android-app::history
  - text: "The User taps Show past period expenses"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::history
  - text: "The User reads each Expense of earlier periods grouped by date"
    kind: actor
    actor: user
    entities:
      - { entity: expense, effect: reads, facts: [Amount, Category, Date] }
    contexts:
      app:
        place: android-app::history
---

# Show past period expenses

## Trigger

The User wants to look back beyond the active period.

## Outcome

Earlier periods' expenses are listed below the current ones.
