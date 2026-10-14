---
kind: primary
routes:
  app: Android app
steps:
  - text: "The finish date of the active Budget period has passed"
    kind: condition
    unattended: true
    entities:
      - { entity: budget-period, effect: reads, facts: [Finish date] }
    contexts:
      app:
        place: android-app::period-end-notification
  - text: "The Product ends the Budget period, keeps what is left as pending extra money and notifies it"
    kind: product
    entities:
      - { entity: budget-period, effect: changes, from: "Active", to: "Ended", facts: [Pending extra money] }
    contexts:
      app:
        place: android-app::period-end-notification
  - text: "When the app is next open, the Product asks what to do with the remaining money"
    kind: product
    entities:
      - { entity: budget-period, effect: reads, facts: [Pending extra money] }
    contexts:
      app:
        place: android-app::period-finished
---

# A period ends with money left

## Trigger

Midnight passes after the last day of a period, with End of period surplus Ask me.

## Outcome

The period has ended and the Period finished question waits for the User (decide-period-surplus).
