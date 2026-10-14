---
kind: primary
routes:
  app: Android app
steps:
  - text: "The User opens Theming and color and changes the theme, colors, font or language"
    kind: actor
    actor: user
    entities:
      - { entity: app-settings, effect: reads, facts: [Theme, Language] }
    contexts:
      app:
        place: android-app::appearance
  - text: "The Product saves the App settings and applies them at once"
    kind: product
    actor: user
    entities:
      - { entity: app-settings, effect: changes, facts: [Theme, Typography, Contrast, Color scheme, Material You, Rounded font, AMOLED theme, Language] }
    contexts:
      app:
        place: android-app::appearance
---

# Change the look and language

## Trigger

The User wants Minus to look or read differently.

## Outcome

The app uses the new appearance and language; System follows the phone's language.

## Edge cases

- The language list warns that translations might be incorrect.
