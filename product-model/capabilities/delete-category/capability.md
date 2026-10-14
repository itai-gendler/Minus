---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/repository/BudgetRepositoryImpl.kt#hideCategory"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/category/EditableCategoryTag.kt"
---

# Delete category

Remove a category from the picker with Delete Category. Expenses keep the category name they were saved with.
