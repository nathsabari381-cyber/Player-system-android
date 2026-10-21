# Player System v3 — Native Android APK project

This is the Android Studio source project for the Solo Leveling-inspired Player System. It includes the previous blue/purple web interface hosted inside a native Android WebView, native Android notification support, fullscreen immersive mode, local browser storage, and boot-persistent daily reminders.

## Simplest route to an APK (no Android Studio required on your phone)
1. Download `player_system_v3_android_source.zip` and extract it.
2. Create a new repository on GitHub.
3. Upload the *contents* of this folder (including `.github/workflows/build-apk.yml`) to the repository's `main` branch.
4. Open the repository's **Actions** tab and select **Build Player System APK**.
5. If it has not run automatically, press **Run workflow**.
6. Wait for the workflow to finish successfully.
7. Open that workflow run, find **Artifacts**, and download `Player-System-debug-APK`.
8. Extract the artifact ZIP on your Android phone and tap `app-debug.apk`.
9. If Android asks, allow your browser/file manager to install unknown apps, then install it.

The generated APK is a debug-signed APK for personal testing, not a Play Store release. Never install APKs from sources you do not trust.

## Build locally with Android Studio
- Open this folder as an existing Android Studio project.
- Use JDK 17 and Android SDK Platform 35.
- Let Gradle sync, then choose **Build → Build Bundle(s) / APK(s) → Build APK(s)**.
- APK output: `app/build/outputs/apk/debug/app-debug.apk`.

## Features
- Full-screen immersive portrait UI
- Player levels, XP, stats, custom quests
- Fitness logging and history
- Study timer and session log
- Streak calendar and skill tree
- XP shop and inventory
- Native Android test notifications and daily reminder alarms
- Re-schedules reminder after device reboot
- WebView DOM storage/localStorage retained between app launches
- JSON export/import backup

## Android notification notes
- Android 13+ requires the user to grant notification permission.
- Exact alarm access rules vary by Android version and device. If exact alarms are unavailable, the app uses an inexact idle-allowed alarm, so delivery can be delayed by battery optimization.
- The app requests notification permission when you enable notifications or schedule a reminder.
- The app has no backend and does not send data to a server. Progress is stored locally; export backups if you need to move devices.
- If Android's app data is cleared or the app is uninstalled, local progress may be removed.

## Notes
- This is a fan-made project and is not affiliated with Solo Leveling's creators.
- The GitHub Actions workflow produces a debug APK automatically; it does not create a Play Store production signing key.
