---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User taps Minus it on a spend reminder"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The Product opens Home with the spotted amount on the numpad"
    kind: product
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The User adds a Category and taps Done"
    kind: actor
    actor: user
    entities:
      - { entity: category, effect: reads, facts: [Name] }
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the Expense in the active Budget period"
    kind: product
    actor: user
    entities:
      - { entity: expense, effect: creates, to: "Recorded", facts: [Amount, Kind, Category, Extra note, Date, Paid with credit card, Credit paid] }
      - { entity: budget-period, effect: reads, facts: [] }
    contexts:
      app:
        place: android-app::home
---

# Record a spotted charge with Minus it

## Trigger

A spend reminder says a charge was spotted in another app's notification.

## Outcome

The charge is recorded with the category the User chose.
