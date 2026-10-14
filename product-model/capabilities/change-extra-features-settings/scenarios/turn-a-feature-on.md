---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens Extra features and turns a feature on"
    kind: actor
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Reserve upcoming charges, Extra note] }
    contexts:
      app:
        place: android-app::extra-features
  - text: "The Product saves the App settings and the feature takes effect"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Credit card payments, Category suggestions on tap, Category list mode, Extra note, Show past transactions, Reserve upcoming charges, Save categories on their own] }
    contexts:
      app:
        place: android-app::extra-features
---

# Turn an extra feature on

## Trigger

The User wants a feature Minus keeps optional.

## Outcome

The feature works across the app, for example the credit card toggle on Home or the extra note field.

## Edge cases

- Category list mode also turns off the numpad's calculation mode while it is on.
