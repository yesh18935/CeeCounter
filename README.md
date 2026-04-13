# CeeCounter

This is a simple cross platform app to count daily calorie intake.

---

## Tech Stack

| Concern          | Choice            |
| ---------------- | ----------------- |
| Framework        | Flutter           |
| Language         | Dart              |
| State management | Riverpod          |
| Navigation       | go_router         |
| Backend          | Firebase          |
| Local DB         | isar / hive (TBD) |

## Requirements

- [Flutter SDK](https://flutter.dev/docs/get-started/install) — Dart SDK `^3.11.4`
- [Android Studio](https://developer.android.com/studio) — includes Android emulator and SDK tools
- Java 17 (recommended: [Eclipse Temurin 17](https://adoptium.net/))

## Setup

```bash
# 1. Verify Flutter is installed correctly
flutter doctor

# 2. Install dependencies
flutter pub get

# 3. Run on Android emulator (start one in Android Studio first)
flutter run
```

If Flutter can't find Java 17, point it explicitly:

```bash
flutter config --jdk-dir "C:\path\to\jdk-17"
```

## Build

```bash
# Android release bundle (upload to Google Play)
flutter build appbundle

# iOS (requires Mac + Xcode)
flutter build ios

# Debug APK (for direct install/testing)
flutter build apk
```

## Tests

```bash
# Run all tests
flutter test

# Run with coverage
flutter test --coverage
```

> Test coverage reporting via `genhtml` (requires lcov):
>
> ```bash
> genhtml coverage/lcov.info -o coverage/html
> ```

Current coverage: _not yet measured_

## Project Structure

```
cee_cleaner/
├── lib/
│   ├── main.dart              # Entry point
│   ├── app.dart               # App widget, routing setup
│   ├── features/              # Feature-based folders
│   │   └── <feature>/
│   │       ├── presentation/  # Widgets, screens
│   │       ├── domain/        # Models, business logic
│   │       └── data/          # Repositories, API/DB access
│   └── shared/                # Shared widgets, utils, theme
├── test/                      # Unit + widget tests
├── android/                   # Android-specific config
├── ios/                       # iOS-specific config
└── pubspec.yaml               # Dependencies
```
