---
appliesTo:
  - type: capability
    id: create-category
  - type: capability
    id: record-expense
  - type: entity
    id: category
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/repository/BudgetRepositoryImpl.kt#findOrCreateCategory"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/local/entity/CategoryEntity.kt"
---

# Category names are unique

Typing a category name that exists reuses that category and counts it as used, and a deleted one with that name is offered again; a new name creates a category.
