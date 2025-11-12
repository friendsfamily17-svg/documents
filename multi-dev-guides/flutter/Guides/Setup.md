# Flutter — Setup

Short description
-----------------
Environment setup and common dependencies to start Flutter development for a typical startup app.

## Install Flutter SDK

1. Follow official instructions: https://flutter.dev/docs/get-started/install
2. Verify: `flutter --version`

## Editor & tools

- VS Code + Flutter extension or Android Studio.
- Recommended extensions: Dart, Flutter, GitLens.

## Common dependencies

- Use `pubspec.yaml` to manage packages. Pin minor versions for stability.
- Run `flutter pub get` after pulling changes.

## Platform setup

- iOS: Xcode and command-line tools (macOS only).
- Android: Android SDK, Java, and emulator images.

## Useful commands

```
flutter pub get
flutter analyze
flutter test
flutter drive --target=test_driver/app.dart
```

## Troubleshooting

- If builds fail after upgrade, run `flutter clean` and `flutter pub get`.
- For dependency conflicts, check transitive package versions and consider overrides as last resort.
