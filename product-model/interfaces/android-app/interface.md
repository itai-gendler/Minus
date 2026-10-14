---
type: mobile-app
actors: [user]
references:
  - { kind: code, role: implementation, target: "app/src/main/java/com/serranoie/app/minus/navigation/AppNavGraph.kt" }
  - { kind: code, role: implementation, target: "app/src/main/java/com/serranoie/app/minus/presentation/MainActivity.kt" }
  - { kind: code, role: context, target: app/src/main/AndroidManifest.xml }
---

# Android app

The Minus phone app. It opens on the onboarding welcome the first time and on Home afterwards,
and it also reaches the person through notifications, home-screen widgets and a Quick Settings
tile. Nothing needs signing in: whoever holds the phone is the User.
