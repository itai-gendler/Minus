---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User types the amount on the numpad"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The User picks a saved Category for it"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: reads, facts: [Name] }
    contexts:
      app:
        place: android-app::home
  - text: "The User taps Done"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the Expense in the active Budget period and counts the Category as used"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: category, effect: changes, facts: [Usage] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
  - text: "The budget pill shows what is left of the Budget period"
    kind: condition
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Remaining] }
    contexts:
      app:
        place: android-app::home
---

# Record an expense with a category

## Trigger

The User spends money and wants it counted.

## Outcome

The expense is recorded today in the active period under that category, and the budget pill drops by its amount.

## Edge cases

- With Extra note turned on in Extra features, an extra note is kept with the expense.
- With no category typed, the expense is recorded without one and shows as Uncategorized in analytics.
