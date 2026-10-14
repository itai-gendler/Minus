---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User dismisses the Period finished question"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::period-finished
  - text: "The User later taps the Pending extra money banner on Home"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, as: ended, effect: reads, facts: [Pending extra money] }
    contexts:
      app:
        place: android-app::home
  - text: "The User chooses Split equally or Add to today"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::period-finished
  - text: "The Product adds the money to the active Budget period at once"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, as: ended, effect: changes, facts: [Pending extra money] }
      - { entity: budget-period, as: active, effect: changes, facts: [Total budget, Carried in] }
    contexts:
      app:
        place: android-app::period-finished
---

# Decide later from the banner

## Trigger

The User put the decision off and has since started a new period.

## Outcome

The money joins the active period immediately, spread or on today.
