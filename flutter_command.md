<div align="center">

# 🦋 Flutter Commands Cheat Sheet

**Every command you need, in the order you'll actually use them, with a one-line explanation of *what it does* and *when to use it*.**

![Flutter](https://img.shields.io/badge/Flutter-02569B?logo=flutter&logoColor=white)
![Dart](https://img.shields.io/badge/Dart-0175C2?logo=dart&logoColor=white)
![Android](https://img.shields.io/badge/Android-3DDC84?logo=android&logoColor=white)
![License](https://img.shields.io/badge/Made%20for-Students-blue)

</div>

---

## 📑 Table of Contents

1. [Quick Start (Start Here)](#-quick-start-start-here)
2. [Installation & Setup](#1-installation--setup)
3. [Create a Project](#2-create-a-project)
4. [Navigate Folders](#3-navigate-folders)
5. [Dependencies (Pub)](#4-dependencies-pub)
6. [Devices & Emulators](#5-devices--emulators)
7. [Run Your App](#6-run-your-app)
8. [Hot Reload & Hot Restart](#7-hot-reload--hot-restart)
9. [Clean Project](#8-clean-project)
10. [Analyze Code](#9-analyze-code)
11. [Format Code](#10-format-code)
12. [Dart Commands](#11-dart-commands)
13. [Testing](#12-testing)
14. [Build Android APK](#13-build-android-apk)
15. [Split APKs](#14-split-apks)
16. [Android App Bundle](#15-android-app-bundle-play-store)
17. [ADB (Install / Uninstall / Logs)](#16-adb-install-uninstall--logs)
18. [Logs & Debugging](#17-logs--debugging)
19. [Other Platforms (Web, Windows, Linux, macOS, iOS)](#18-other-platforms)
20. [Configuration](#19-flutter-configuration)
21. [Channels & SDK Upgrades](#20-channels--sdk-management)
22. [Code Generation](#21-code-generation)
23. [App Icons & Splash Screen](#22-app-icons--splash-screen)
24. [Firebase](#23-firebase-with-flutter)
25. [Git](#24-git-for-flutter-projects)
26. [Troubleshooting](#25-troubleshooting)
27. [Project Structure](#26-project-structure)

---

## ⚡ Quick Start (Start Here)

> You don't need to memorize everything. For **students building simple apps and turning them into installable Android apps**, this is the whole journey:

```bash
flutter create my_app            # 1. Make a new project
cd my_app                        # 2. Go inside it
flutter pub get                  # 3. Download dependencies
flutter run                      # 4. Run it on a device
flutter build apk --release      # 5. Create the installable APK
```

📦 Your APK will be at: `build/app/outputs/flutter-apk/app-release.apk`

### 🧠 The 15 Commands Worth Memorizing

| Command | Purpose |
|---|---|
| `flutter doctor` | Check if Flutter is installed correctly |
| `flutter create my_app` | Create a new project |
| `cd my_app` | Enter the project folder |
| `flutter pub get` | Download the project's packages |
| `flutter devices` | See where you can run the app |
| `flutter run` | Run the app |
| `flutter clean` | Delete build files to fix weird errors |
| `flutter analyze` | Find errors and warnings in code |
| `flutter test` | Run your tests |
| `flutter pub add package_name` | Add a package |
| `flutter pub remove package_name` | Remove a package |
| `flutter build apk --release` | Build the final Android APK |
| `flutter build appbundle --release` | Build the file for Google Play |
| `flutter build web` | Build a website version |
| `dart format .` | Auto-format all code neatly |

---

## 1. Installation & Setup

> **Use these first**, right after installing Flutter, to confirm everything works.

| Command | Purpose / When to use |
|---|---|
| `flutter --version` | Shows your installed Flutter and Dart version. Use it to confirm installation or report your version in a bug. |
| `flutter doctor` | Checks your whole setup (SDK, Android Studio, devices) and lists problems. Run it first on any new machine. |
| `flutter doctor -v` | Same as above with full detail. Use it when `flutter doctor` shows an error and you need to know why. |
| `flutter help` | Lists every available Flutter command. Use it when you forget a command name. |
| `flutter help run` | Shows all options for one specific command. Replace `run` with any command (e.g. `build`). |

---

## 2. Create a Project

| Command | Purpose / When to use |
|---|---|
| `flutter create my_app` | Creates a brand new Flutter app in a folder named `my_app`. |
| `flutter create --org com.example my_app` | Same, but sets your package/organization name (becomes `com.example.my_app`). Use it for apps you plan to publish. |
| `flutter create --platforms=android my_app` | Creates the app for **Android only**, keeping the project small. |
| `flutter create --platforms=android,web,windows my_app` | Creates the app for several chosen platforms at once. |
| `flutter create .` | Creates a Flutter project **inside the current folder** instead of making a new one. |

---

## 3. Navigate Folders

> Basic terminal commands you need to get around.

| Command | Purpose / When to use |
|---|---|
| `cd my_app` | Moves into the project folder. Do this before running any Flutter command on the project. |
| `cd ..` | Goes back one folder. |
| `dir` | Lists files in the current folder (**Windows**). |
| `ls` | Lists files in the current folder (**Linux / macOS**). |

---

## 4. Dependencies (Pub)

> Packages are ready-made code libraries (like `http` or `provider`) listed in `pubspec.yaml`.

| Command | Purpose / When to use |
|---|---|
| `flutter pub get` | Downloads all packages listed in `pubspec.yaml`. Run after creating, cloning, or editing dependencies. |
| `flutter pub upgrade` | Updates packages to the newest versions allowed by your `pubspec.yaml`. |
| `flutter pub upgrade --major-versions` | Updates packages even across major versions (may break your code, so test after). |
| `flutter pub add http` | Adds the `http` package to your project automatically. Replace with any package name. |
| `flutter pub add provider` | Example: adds the `provider` state-management package. |
| `flutter pub add --dev flutter_lints` | Adds a **development-only** package (used while coding/testing, not shipped in the app). |
| `flutter pub remove http` | Removes a package from your project. |
| `flutter pub deps` | Shows the full tree of packages your app depends on. |
| `flutter pub outdated` | Lists packages that have newer versions available. |

---

## 5. Devices & Emulators

| Command | Purpose / When to use |
|---|---|
| `flutter devices` | Lists everything you can run on (Chrome, Windows, a phone, an emulator). Check this before `flutter run`. |
| `flutter emulators` | Lists the Android/iOS emulators installed on your computer. |
| `flutter emulators --launch <emulator_id>` | Starts a chosen emulator. Example: `flutter emulators --launch Pixel_8`. |

---

## 6. Run Your App

| Command | Purpose / When to use |
|---|---|
| `flutter run` | Runs the app on the connected device (debug mode). Your everyday command. |
| `flutter run -d <device_id>` | Runs on a specific device. Example: `flutter run -d chrome`. |
| `flutter run --debug` | Debug mode: slower, but gives hot reload and error details. (Default.) |
| `flutter run --profile` | Profile mode: used to measure app **performance** on a real device. |
| `flutter run --release` | Release mode: fast and optimized, like the final app. Use it to check real-world speed. |

---

## 7. Hot Reload & Hot Restart

> Keys you press **in the terminal while `flutter run` is active**. This is Flutter's superpower: see changes instantly.

| Key | Purpose / When to use |
|---|---|
| `r` | **Hot reload.** Applies code changes instantly and keeps app state. Use after small UI edits. |
| `R` | **Hot restart.** Restarts the app from scratch (state is reset). Use when hot reload doesn't pick up a change. |
| `h` | Shows the list of all available keys. |
| `q` | Quits the running app. |

---

## 8. Clean Project

| Command | Purpose / When to use |
|---|---|
| `flutter clean` | Deletes old build files. Use it when you see strange or unexplained build errors. |

**Common fix sequence** (solves a huge share of problems):

```bash
flutter clean
flutter pub get
flutter run
```

---

## 9. Analyze Code

| Command | Purpose / When to use |
|---|---|
| `flutter analyze` | Scans your code for errors, warnings, unused imports, and type problems. Run it before building. |
| `flutter analyze lib/` | Scans only one folder (here, `lib/`). |

---

## 10. Format Code

| Command | Purpose / When to use |
|---|---|
| `dart format .` | Automatically tidies the formatting of **all** your code. |
| `dart format lib/main.dart` | Formats **one file** only. |
| `dart format --output=none --set-exit-if-changed .` | Only **checks** formatting without changing files. Handy in CI/automation. |

---

## 11. Dart Commands

> Flutter apps are written in the **Dart** language, so Dart's own tools are useful too.

| Command | Purpose / When to use |
|---|---|
| `dart --version` | Shows your Dart version. |
| `dart --help` | Lists all Dart commands. |
| `dart run file.dart` | Runs a plain Dart file (no Flutter UI). Great for practicing Dart basics. |
| `dart analyze` | Checks Dart code for problems. |
| `dart format .` | Formats Dart code. |

---

## 12. Testing

| Command | Purpose / When to use |
|---|---|
| `flutter test` | Runs all tests in the `test/` folder. Run before releasing. |
| `flutter test test/widget_test.dart` | Runs one specific test file. |
| `flutter test --coverage` | Runs tests and measures how much code they cover. Report is saved in `coverage/`. |

---

## 13. Build Android APK

> An **APK** is the installable file you can share and install on any Android phone.

| Command | Purpose / When to use |
|---|---|
| `flutter build apk --debug` | Builds a debug APK, good for quick testing (larger, slower). |
| `flutter build apk --release` | Builds the **final, optimized APK** to share or install. |
| `flutter build apk --profile` | Builds an APK for performance testing. |

📍 Release APK location:

```text
build/app/outputs/flutter-apk/app-release.apk
```

---

## 14. Split APKs

| Command | Purpose / When to use |
|---|---|
| `flutter build apk --split-per-abi` | Creates **smaller APKs, one per CPU type**, instead of one large APK. Use it to reduce file size. |

Output example:

```text
app-arm64-v8a-release.apk      ← most modern phones (use this one)
app-armeabi-v7a-release.apk    ← older phones
app-x86_64-release.apk         ← emulators / some tablets
```

---

## 15. Android App Bundle (Play Store)

| Command | Purpose / When to use |
|---|---|
| `flutter build appbundle --release` | Builds an `.aab` file, which is **required for uploading to Google Play**. |

📍 Location:

```text
build/app/outputs/bundle/release/app-release.aab
```

---

## 16. ADB (Install / Uninstall / Logs)

> **ADB** (Android Debug Bridge) talks directly to your Android phone.

| Command | Purpose / When to use |
|---|---|
| `adb devices` | Lists connected Android devices. Use it to confirm your phone is detected. |
| `adb install app-release.apk` | Installs an APK onto the connected phone. Use the real path to your APK. |
| `adb uninstall com.example.myapp` | Removes an app using its package name. |
| `adb logcat` | Shows the raw system logs from the Android device. |

---

## 17. Logs & Debugging

| Command | Purpose / When to use |
|---|---|
| `flutter logs` | Shows live logs from your running app. Use it to see `print()` output and errors. |
| `flutter run -v` | Runs with **very detailed (verbose)** output. Use it when a build or device problem is hard to diagnose. |

---

## 18. Other Platforms

Flutter builds for more than Android. Enable the platform, run it, then build it.

### 🌐 Web

| Command | Purpose / When to use |
|---|---|
| `flutter config --enable-web` | Turns on web support (usually already on). |
| `flutter run -d chrome` | Runs the app in the Chrome browser. |
| `flutter build web` | Builds a website, output in `build/web/`. |

### 🪟 Windows

| Command | Purpose / When to use |
|---|---|
| `flutter config --enable-windows-desktop` | Turns on Windows desktop support. |
| `flutter run -d windows` | Runs the app as a Windows program. |
| `flutter build windows` | Builds a Windows app. |

### 🐧 Linux

| Command | Purpose / When to use |
|---|---|
| `flutter config --enable-linux-desktop` | Turns on Linux desktop support. |
| `flutter run -d linux` | Runs the app on Linux. |
| `flutter build linux` | Builds a Linux app. |

### 🍎 macOS

| Command | Purpose / When to use |
|---|---|
| `flutter config --enable-macos-desktop` | Turns on macOS desktop support. |
| `flutter run -d macos` | Runs the app on macOS. |
| `flutter build macos` | Builds a macOS app. |

### 📱 iOS (requires a Mac with Xcode)

| Command | Purpose / When to use |
|---|---|
| `flutter devices` | Lists connected iPhones and simulators. |
| `flutter run -d ios` | Runs the app on an iOS device/simulator. |
| `flutter build ios` | Builds the iOS app. |
| `flutter build ios --no-codesign` | Builds iOS without signing. Useful for testing the build or in CI. |

> 💡 iOS support is normally enabled automatically on macOS, so no extra config command is usually needed.

---

## 19. Flutter Configuration

| Command | Purpose / When to use |
|---|---|
| `flutter config` | Shows your current Flutter settings. |
| `flutter config --enable-web` | Turns **on** a platform. Example: `--enable-windows-desktop`. |
| `flutter config --no-enable-web` | Turns **off** a platform you don't need. |

---

## 20. Channels & SDK Management

> Channels are Flutter release tracks: **stable** (safe), **beta** (newer), **main** (latest, may break).

| Command | Purpose / When to use |
|---|---|
| `flutter channel` | Shows the current channel and lists the others. |
| `flutter channel stable` | Switches to the stable channel. **Recommended for beginners.** |
| `flutter channel beta` | Switches to beta for upcoming features. |
| `flutter channel main` | Switches to the cutting-edge channel (can be unstable). |
| `flutter upgrade` | Updates Flutter to the latest version on your channel. |
| `flutter downgrade` | Goes back to the previous Flutter version if an update broke something. |

> 💡 After switching channels, run `flutter upgrade` to finish the switch.

---

## 21. Code Generation

> Some packages (e.g. JSON serialization, Hive, Freezed) generate code for you.

| Command | Purpose / When to use |
|---|---|
| `dart run build_runner build` | Generates the code once. |
| `dart run build_runner watch` | Keeps running and regenerates code whenever you save a file. |
| `dart run build_runner build --delete-conflicting-outputs` | Deletes old generated files and rebuilds. Use it when you get "conflicting outputs" errors. |

---

## 22. App Icons & Splash Screen

### 🎨 App icon (`flutter_launcher_icons`)

| Command | Purpose / When to use |
|---|---|
| `flutter pub add flutter_launcher_icons` | Adds the icon package. |
| `dart run flutter_launcher_icons` | Generates your app icon for every size after you configure it in `pubspec.yaml`. |

### 💦 Splash screen (`flutter_native_splash`)

| Command | Purpose / When to use |
|---|---|
| `flutter pub add flutter_native_splash` | Adds the splash screen package. |
| `dart run flutter_native_splash:create` | Generates the launch screen after you configure it in `pubspec.yaml`. |

---

## 23. Firebase with Flutter

> Firebase gives you login, database, notifications, and more. Install the [Firebase CLI](https://firebase.google.com/docs/cli) first.

| Command | Purpose / When to use |
|---|---|
| `firebase login` | Signs you in to your Firebase/Google account. |
| `dart pub global activate flutterfire_cli` | Installs the FlutterFire tool (one-time setup). |
| `flutterfire configure` | Connects your Flutter app to a Firebase project automatically. |
| `flutter pub add firebase_core` | Adds the core Firebase package (required by all other Firebase packages). |

---

## 24. Git for Flutter Projects

| Command | Purpose / When to use |
|---|---|
| `git init` | Starts tracking your project with Git. |
| `git status` | Shows which files changed. |
| `git add .` | Stages all changes for the next commit. |
| `git commit -m "Initial Flutter app"` | Saves a snapshot of your work with a message. |
| `git remote add origin <repository-url>` | Links your project to a GitHub repository. |
| `git push -u origin main` | Uploads your code to GitHub. |

---

## 25. Troubleshooting

> App won't build or run? Try these in order.

| Command | Purpose / When to use |
|---|---|
| `flutter clean` | Removes old build files. |
| `flutter pub get` | Re-downloads packages. |
| `flutter doctor` | Checks your setup for problems. |
| `flutter devices` | Confirms a device is available. |
| `flutter pub outdated` | Finds packages that might be causing version conflicts. |
| `flutter run -v` | Shows detailed logs to find the real cause. |

**Full recovery sequence:**

```bash
flutter clean
flutter pub get
flutter doctor
flutter devices
flutter run
```

---

## 26. Project Structure

After `flutter create my_app` you'll see:

```text
my_app/
│
├── android/          # Android-specific code & settings
├── ios/              # iOS-specific code & settings
├── lib/              # ⭐ Your Dart code lives here
│   └── main.dart     # ⭐ App entry point
├── test/             # Your test files
├── web/              # Web-specific files
├── windows/          # Windows-specific files
├── linux/            # Linux-specific files
├── macos/            # macOS-specific files
├── pubspec.yaml      # ⭐ Packages, assets, app settings
├── pubspec.lock      # Exact package versions (auto-generated)
└── README.md         # Project description
```

| File / Folder | What it's for |
|---|---|
| `lib/main.dart` | Where your app starts running. |
| `pubspec.yaml` | Where you declare packages, fonts, and images. |
| `pubspec.lock` | Auto-generated; locks exact package versions. Don't edit by hand. |

---

## 🚀 Complete Development Workflow

Your full journey for a **new Android app**, from zero to installable APK:

```bash
# 1. Check installation
flutter doctor

# 2. Create project
flutter create my_app

# 3. Enter project
cd my_app

# 4. Install dependencies
flutter pub get

# 5. Check devices
flutter devices

# 6. Run application
flutter run

# 7. Add packages when needed
flutter pub add http

# 8. Analyze code
flutter analyze

# 9. Format code
dart format .

# 10. Test
flutter test

# 11. Clean before final build
flutter clean

# 12. Get dependencies again
flutter pub get

# 13. Create release APK
flutter build apk --release
```

---

<div align="center">

⭐ **Found this helpful? Star the repo and share it with fellow learners!** ⭐

*Happy Fluttering! 🦋*

</div>