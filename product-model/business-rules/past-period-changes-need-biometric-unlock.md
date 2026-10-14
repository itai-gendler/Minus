---
appliesTo:
  - type: capability-scenario
    id: edit-a-past-period-expense
  - type: capability-scenario
    id: delete-a-past-period-expense
  - type: capability-scenario
    id: remove-a-past-charge
  - type: capability
    id: delete-past-period
references:
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/Analytics.kt"
  - kind: code
    role: implementation
    target: "app/src/main/java/com/serranoie/app/minus/presentation/util/BiometricPromptHelper.kt"
---

# Changing a past period needs confirmation and a biometric unlock

Editing or deleting an expense of a past period, removing one of its recurring charges, and deleting a past period each ask for confirmation and then a fingerprint before anything changes.

## Rationale

Past periods are the record of what was spent; a deliberate unlock keeps them from being changed by accident.
