---
kind: validation
routes:
  app: Android app
steps:
  - text: "The User sets a Custom split whose three values do not add up to 100%"
    kind: actor
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
  - text: "The Product says the values must add up to 100% and does not save"
    kind: condition
    actor: user
    entities: []
    contexts:
      app:
        place: android-app::settings
---

# A custom split that does not add up

## Trigger

Custom percentages are tuned by hand.

## Outcome

The current total is shown and the preferences stay as they were.

## Edge cases

- Reset to defaults returns to the Balanced split with no goal.
