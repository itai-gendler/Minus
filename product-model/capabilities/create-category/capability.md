---
availability:
  - { place: android-app }
domain: expenses
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/repository/BudgetRepositoryImpl.kt#createCategory"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/category/NewCategoryTag.kt"
---

# Create category

Add a category from the category picker, or, with Save categories on their own on, from the New category tag on Home without recording any amount. Creating a deleted category's name brings it back.
