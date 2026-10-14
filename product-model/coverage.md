---
scope: The Minus phone app, its Wear OS companion and the watch sync contract at commit 794e5f6.
method: Static reading of screens, view models, use cases, repositories, workers, receivers, string resources and project docs; no code was run.
covered:
  - description: Phone app screens, view models and the components that carry product behavior.
    paths:
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/home/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/editor/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/budget/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/history/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/subscriptions/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/analytics/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/onboarding/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/Settings.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/SettingsScreen.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/SettingsViewModel.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/appearance/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/features/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/savings/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/csv/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/components/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/component/
      - app/src/main/java/com/serranoie/app/minus/presentation/MainActivity.kt
      - app/src/main/java/com/serranoie/app/minus/navigation/AppNavGraph.kt
      - app/src/main/java/com/serranoie/app/minus/navigation/Screen.kt
  - description: Domain models, calculators, period logic and use cases.
    paths:
      - app/src/main/java/com/serranoie/app/minus/domain/model/BudgetPeriodModel.kt
      - app/src/main/java/com/serranoie/app/minus/domain/model/BudgetState.kt
      - app/src/main/java/com/serranoie/app/minus/domain/model/ArchivedBudget.kt
      - app/src/main/java/com/serranoie/app/minus/domain/model/Category.kt
      - app/src/main/java/com/serranoie/app/minus/domain/model/CreditCard.kt
      - app/src/main/java/com/serranoie/app/minus/domain/model/TransactionModel.kt
      - app/src/main/java/com/serranoie/app/minus/domain/model/UserSettingsModel.kt
      - app/src/main/java/com/serranoie/app/minus/domain/model/SavingsPreferences.kt
      - app/src/main/java/com/serranoie/app/minus/domain/model/PeriodKey.kt
      - app/src/main/java/com/serranoie/app/minus/domain/calculator/ExpressionEvaluator.kt
      - app/src/main/java/com/serranoie/app/minus/domain/calculator/RecurringExpenseCalculator.kt
      - app/src/main/java/com/serranoie/app/minus/domain/notification/
      - app/src/main/java/com/serranoie/app/minus/domain/time/
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/AddTransactionUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/DeleteTransactionUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/ClearEarlyFinishStateUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/FinishBudgetEarlyUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/GetCurrentPeriodIdUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/MarkOnboardingCompletedUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/ObserveCurrentPeriodBoundaryUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/ObserveCurrentPeriodRolloverUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/PersistBudgetSettingsUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/UpdatePeriodEndNotificationTimeUseCase.kt
  - description: Persistence, repositories and CSV import, export and folder sync.
    paths:
      - app/src/main/java/com/serranoie/app/minus/data/local/AppDatabase.kt
      - app/src/main/java/com/serranoie/app/minus/data/local/dao/
      - app/src/main/java/com/serranoie/app/minus/data/local/entity/
      - app/src/main/java/com/serranoie/app/minus/data/repository/BudgetRepository.kt
      - app/src/main/java/com/serranoie/app/minus/data/repository/BudgetRepositoryImpl.kt
      - app/src/main/java/com/serranoie/app/minus/data/repository/SettingsRepository.kt
      - app/src/main/java/com/serranoie/app/minus/data/repository/SettingsRepositoryImpl.kt
      - app/src/main/java/com/serranoie/app/minus/data/csv/
  - description: Notifications, alarms, reminder workers, notification actions, spend reminder listener, widgets and the Quick Settings tile.
    paths:
      - app/src/main/java/com/serranoie/app/minus/presentation/notification/
      - app/src/main/java/com/serranoie/app/minus/presentation/widget/
      - app/src/main/java/com/serranoie/app/minus/presentation/tile/
      - app/src/main/java/com/serranoie/app/minus/presentation/util/CensorManager.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/util/BiometricPromptHelper.kt
  - description: Phone side of the watch connection, the watch app and their shared protocol.
    paths:
      - app/src/wear/java/
      - app/src/foss/java/
      - wear/src/main/java/
      - sync-contract/src/main/
  - description: Default user-facing strings and the app manifests.
    paths:
      - app/src/main/res/values/strings.xml
      - wear/src/main/res/values/strings.xml
      - app/src/main/AndroidManifest.xml
      - wear/src/main/AndroidManifest.xml
exclusions:
  - description: Theme, color schemes, typography, the color harmonization library and navigation animations.
    paths:
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/Color.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/Shape.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/Theme.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/ThemeManager.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/Type.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/harmonize/
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/theme/schemes/
      - app/src/main/java/com/serranoie/app/minus/navigation/BackMotion.kt
      - app/src/main/java/com/serranoie/app/minus/navigation/PredictiveDismiss.kt
      - wear/src/main/java/com/serranoie/app/wear/minus/presentation/theme/
  - description: Formatting, haptics, layout and permission helpers with no product behavior of their own.
    paths:
      - app/src/main/java/com/serranoie/app/minus/presentation/util/ColorUtils.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/util/StatusBarPadding.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/util/Utils.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/util/HardwareKeyHandler.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/util/font/
      - app/src/main/java/com/serranoie/app/minus/presentation/util/haptic/
      - app/src/main/java/com/serranoie/app/minus/presentation/util/CensorUtils.kt
      - app/src/main/java/com/serranoie/app/minus/presentation/permission/
  - description: Dependency injection, application setup and time providers.
    paths:
      - app/src/main/java/com/serranoie/app/minus/data/di/
      - app/src/main/java/com/serranoie/app/minus/MinusApplication.kt
      - wear/src/main/java/com/serranoie/app/wear/minus/WearApplication.kt
  - description: Translations, images and other resources, mirrored from the default strings.
    paths:
      - app/src/main/res/
      - wear/src/main/res/
      - wear/src/beta/
      - app/src/beta/
  - description: Tests, used as leads only.
    paths:
      - app/src/test/
      - app/src/androidTest/
      - sync-contract/src/test/
  - description: Build, release, store listing, promotional material, CI and project tooling.
    paths:
      - build.gradle.kts
      - settings.gradle.kts
      - gradle.properties
      - gradle/
      - gradlew
      - gradlew.bat
      - app/build.gradle.kts
      - wear/build.gradle.kts
      - sync-contract/build.gradle.kts
      - config/
      - .github/
      - .run/
      - fastlane/
      - promo/
      - assets/
      - Gemfile
      - crowdin.yml
      - version.properties
      - app/schemas/
unmapped:
  - description: Widget gallery in Settings that pins widgets to the home screen.
    paths:
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/widgets/
  - description: What's new sheet and changelog history shown after updates.
    paths:
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/changelog/
      - app/src/main/java/com/serranoie/app/minus/domain/model/changelog/
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/ChangelogTriggerEvaluator.kt
      - app/src/main/java/com/serranoie/app/minus/data/repository/ChangelogRepository.kt
  - description: Bug report form, its zip attachment and the error log it collects.
    paths:
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/settings/bugreport/
      - app/src/main/java/com/serranoie/app/minus/presentation/util/ErrorLogRecorder.kt
  - description: First-launch tutorial boxes and their progress.
    paths:
      - app/src/main/java/com/serranoie/app/minus/presentation/ui/tutorial/
      - app/src/main/java/com/serranoie/app/minus/domain/model/FirstLaunchTutorialStage.kt
  - description: One-time data migrations run at app start, and the database migrations.
    paths:
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/BackfillOrphanedPeriodsUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/domain/usecase/FoldCarryIntoTotalBudgetUseCase.kt
      - app/src/main/java/com/serranoie/app/minus/data/local/AppDatabaseMigrations.kt
limitations:
  - description: Period mapping mode, kept as a setting with no control that changes it, and the mapper it selects.
    paths:
      - app/src/main/java/com/serranoie/app/minus/domain/model/PeriodMappingMode.kt
      - app/src/main/java/com/serranoie/app/minus/domain/calculator/TransactionPeriodMapper.kt
---

# Coverage
