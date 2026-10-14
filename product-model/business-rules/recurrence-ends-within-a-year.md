---
appliesTo:
  - type: capability
    id: add-recurring-expense
  - type: capability
    id: edit-recurring-expense
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/dialogs/RecurrentExpenseDialog.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/history/edit/RecurrenceConfigSheet.kt"
---

# A recurrence ends after today and within twelve months

The limit date or recurrence end of a recurring expense can only be a day after today and no more than twelve months ahead.
