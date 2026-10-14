---
entities:
  - { entity: budget-period, shows: [Start date, Finish date, Total budget, Spent] }
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/dialogs/PastPeriodsBottomSheet.kt"
---

# Past periods

The list of past budget periods with what was spent against each limit and whether it was on track, over budget or saved money; tapping one opens its breakdown and a long press deletes it.
