---
entities:
  - { entity: app-settings, shows: [Credit card payments, Category suggestions on tap, Category list mode, Extra note, Show past transactions, Reserve upcoming charges, Save categories on their own, Spend reminders], collects: [Credit card payments, Category suggestions on tap, Category list mode, Extra note, Show past transactions, Reserve upcoming charges, Save categories on their own] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/features/FeatureLabScreen.kt"
---

# Extra features

Optional and experimental features, each off by default, with what it changes: credit card payments, category behavior, the extra note, past transactions, reserving upcoming charges, saving categories on their own, spend reminders and the CSV folder sync guide.
