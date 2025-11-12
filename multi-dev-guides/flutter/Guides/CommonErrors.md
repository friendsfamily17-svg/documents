# Flutter — Common Errors & Quick Fixes

Short description
-----------------
Common issues new Flutter developers hit and quick ways to resolve them.

## 1. Missing packages after pull

- Symptom: `Target of URI doesn't exist: 'package:...'.`
- Fix: `flutter pub get` and restart your IDE.

## 2. CocoaPods issues (iOS)

- Symptom: Xcode error during pod install.
- Fix: `cd ios && pod install --repo-update` and ensure CocoaPods is up to date.

## 3. AndroidX / Gradle version mismatches

- Symptom: Gradle build fails after dependency updates.
- Fix: check `android/gradle.properties` and `build.gradle` versions; run `./gradlew clean`.

## 4. Hot reload not applying

- Symptom: UI doesn't update after hot reload.
- Fix: Try full restart or `flutter clean` if stateful code changed significantly.

## 5. Unexpected null errors

- Symptom: runtime null-safety exceptions.
- Fix: audit nullable types and ensure safe handling or migration to NNBD where appropriate.
