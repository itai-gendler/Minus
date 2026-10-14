---
kind: alternative
routes:
  watch: Wear OS watch
steps:
  - text: "The User taps the add button on the watch"
    kind: actor
    actor: user
    entities: []
    contexts:
      watch:
        place: wear-app::period-overview
  - text: "The User types the amount on the watch numpad"
    kind: actor
    actor: user
    entities: []
    contexts:
      watch:
        place: wear-app::expense-entry
  - text: "The User picks a suggested Category or types one and taps Save"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: reads, facts: [Name] }
    contexts:
      watch:
        place: wear-app::expense-entry
  - text: "The Product keeps the Expense on the watch and starts sending it to the phone"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Waiting for phone", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
    contexts:
      watch:
        place: wear-app::expense-entry
---

# Record an expense on the watch

## Trigger

The User spends money with the watch at hand.

## Outcome

The watch vibrates, keeps the expense and sends it to the phone, where it is recorded in the active period (sync-with-phone).
