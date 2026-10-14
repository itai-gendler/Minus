---
kind: alternative
routes:
  app: Android app
steps:
  - text: "The User chooses Add it all to today"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::home
  - text: "The Product records the choice for today and adds the leftover to today's allowance in the Budget period"
    kind: product
    actor: user
    entities:
      - { entity: budget-period, effect: changes, facts: [Leftover choices] }
    contexts:
      app:
        place: android-app::home
---

# Add yesterday's leftover to today

## Trigger

The User wants to spend yesterday's savings today.

## Outcome

Today's allowance includes the whole leftover; the days after keep their amount.
