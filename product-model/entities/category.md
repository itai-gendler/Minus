---
domain: expenses
relations:
  - entity: expense
    verb: tags
    cardinality: one-to-many
  - entity: recurring-expense
    verb: tags
    cardinality: one-to-many
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/domain/model/Category.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/data/local/dao/CategoryDao.kt"
---

# Category

A name expenses are tagged with and grouped by in analytics.

## Information kept

- **Name** — the category's name, unique among categories
- **Usage** — how often and how recently it was used, which orders the suggestions

## States

### Active

Offered when tagging an expense.

### Deleted

No longer offered; using its name again brings it back.
