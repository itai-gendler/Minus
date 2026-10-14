---
entities:
  - { entity: expense, collects: [Amount, Category] }
  - { entity: category, shows: [Name] }
references:
  - kind: code
    role: implementation
    target: "wear/src/main/java/com/serranoie/app/wear/minus/presentation/NumpadEntryScreen.kt"
  - kind: code
    role: implementation
    target: "wear/src/main/java/com/serranoie/app/wear/minus/presentation/CategoryDecEntryScreen.kt"
---

# Expense entry

The watch numpad for the amount, then the category step with suggestions from the phone.
