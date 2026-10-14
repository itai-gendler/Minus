---
kind: edge
routes:
  app: Android app
steps:
  - text: "A watched app posts a notification about a refund, a deposit, a code or a promotion"
    kind: condition
    unattended: true
    entities:
      - { entity: app-settings, effect: reads, facts: [Apps to watch] }
    contexts:
      app:
        place: android-app::spend-reminder-notification
  - text: "The Product posts nothing"
    kind: product
    entities: []
    contexts:
      app:
        place: android-app::spend-reminder-notification
---

# A notification that is not a charge

## Trigger

The notification mentions a refund, deposit, balance, cashback, a one-time code, a discount or a promo, or shows the amount after a +.

## Outcome

No spend reminder appears.
