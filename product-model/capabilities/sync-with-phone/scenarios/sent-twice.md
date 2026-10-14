---
kind: edge
routes:
  watch: Wear OS watch
steps:
  - text: "The phone receives an Expense it has already recorded from the watch"
    kind: condition
    unattended: true
    entities:
      - { entity: expense, effect: reads, facts: [] }
    contexts:
      watch:
        place: wear-app::period-overview
  - text: "The Product acknowledges it without recording it again"
    kind: product
    entities:
      - { entity: expense, effect: reads, facts: [] }
    contexts:
      watch:
        place: wear-app::period-overview
---

# An expense reaches the phone twice

## Trigger

An acknowledgement was lost and the watch sent the expense again.

## Outcome

The expense is recorded only once on the phone.
