---
singleton: true
domain: settings
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/UserSettingsModel.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/repository/SettingsRepositoryImpl.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/SavingsPreferences.kt"
---

# App settings

The person's preferences for Minus on this phone.

## Information kept

- **Onboarding completed** — whether the welcome has been completed
- **Budget view** — Daily, Weekly, Biweekly or Monthly: which allowance the budget pill shows
- **Theme** — Light, Dark or Follow system
- **Typography** — Default, Condensed or Expressive
- **Contrast** — Normal, Medium or High
- **Color scheme** — the chosen color scheme
- **Material You** — whether wallpaper colors theme the app
- **Rounded font** — whether the rounded font style is used
- **AMOLED theme** — whether dark mode uses pure black
- **Language** — the app language, or the system's
- **Privacy mode** — whether financial values are blurred while the app is open
- **Period end time** — the time the period end notification is shown
- **Recurring payments time** — the time recurring payment reminders and the credit card reminder are shown
- **Savings split** — the needs, wants and savings percentages: Balanced, Aggressive saver, Conservative or Custom
- **Savings goal** — an optional target amount and number of months
- **Credit card payments** — whether expenses can be marked as paid with the credit card
- **Show past transactions** — whether the history can load past periods' expenses
- **Category suggestions on tap** — whether tapping the category field lists every saved category
- **Category list mode** — whether the category tag opens a grid of saved categories
- **Extra note** — whether expenses take an extra note
- **Reserve upcoming charges** — whether recurring charges due later in the period are set aside from day one
- **Save categories on their own** — whether Home offers a New category tag
- **Spend reminders** — whether other apps' notifications are watched for charges
- **Apps to watch** — the apps whose notifications spend reminders read
- **Sync folder** — the folder a CSV copy is kept in
- **Last sync** — when the folder last synced and how it went
