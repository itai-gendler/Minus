---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User asks to delete a Recurring expense in Subscriptions"
    kind: actor
    actor: user
    entities:
      - { entity: recurring-expense, effect: reads, facts: [Category] }
    contexts:
      app:
        place: android-app::subscriptions
  - text: "The User confirms the deletion"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::subscriptions
  - text: "The Product deletes the Recurring expense with every Recurring payment settled for it and cancels its reminders"
    kind: product
    actor: user
    entities:
      - { entity: recurring-expense, effect: removes }
      - { entity: recurring-payment, effect: removes, from: "Paid", with: recurring-expense }
    contexts:
      app:
        place: android-app::subscriptions
---

# Delete a subscription

## Trigger

The User cancelled a subscription.

## Outcome

It is no longer charged, listed or reminded.

## Edge cases

- Deleting it from the history works the same way.
- If it cannot be deleted, Could not delete this subscription is shown.
