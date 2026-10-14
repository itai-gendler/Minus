---
type: device
actors: [user]
languages: [en, ru]
references:
  - { kind: code, role: implementation, target: "wear/src/main/java/com/serranoie/app/wear/minus/presentation/MainActivity.kt" }
  - { kind: code, role: implementation, target: sync-contract/src/main/kotlin/com/serranoie/app/minus/sync/contract/WearSyncProtocol.kt }
  - { kind: doc, role: context, target: PROJECT_OVERVIEW.md, title: Wear OS integration }
---

# Wear OS watch

The Minus Wear OS companion app. It shows the budget the paired phone sends and records expenses
from the wrist. It works with the phone app build that carries the watch connection (the "wear"
build); the FOSS build has no watch connection.
