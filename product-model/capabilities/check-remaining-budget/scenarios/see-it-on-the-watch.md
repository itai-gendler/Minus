---
kind: alternative
routes:
  watch: Wear OS watch
steps:
  - text: "The User opens Minus on the watch"
    kind: actor
    actor: user
    entities:
      - { entity: budget-period, effect: reads, facts: [Remaining, Total budget, Spent, Finish date] }
    contexts:
      watch:
        place: wear-app::period-overview
---

# See it on the watch

## Trigger

The User glances at the watch.

## Outcome

The overview shows what is left today or how far over budget, and the days left, as last sent by the phone.
