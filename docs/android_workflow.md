# Android Development Workflow Guide

This guide details the process for running your Flutter application on the Android emulator (`lasbook`) without needing to open the full Android Studio IDE.

## 1. Launch the Emulator

Start the Android emulator from your terminal.

```bash
flutter emulators --launch lasbook
```

> **Note:** If the emulator is already running, you can skip this step.

## 2. Run the Application

Navigate to your project directory and run the app.

### Debug Mode (Default)
Best for development with Hot Reload support.

```bash
flutter run
```

If multiple devices are connected (e.g., iOS Simulator + Android Emulator), specify the device ID:

```bash
# Check connected devices
flutter devices

# Run on specific device (replace <device-id> with actual ID, e.g., emulator-5554)
flutter run -d emulator-5554
```

### Release Mode
Use this to test performance or before deploying. Note that Hot Reload is **not** available in release mode.

```bash
flutter run --release
```

## 3. Development Commands

While the app is running in the terminal, you can use the following keys:

| Key | Action | Description |
| :--- | :--- | :--- |
| `r` | **Hot Reload** | Quickly applies code changes without restarting the app. |
| `R` | **Hot Restart** | Rebuilds the app state from scratch (slower than reload). |
| `h` | **Help** | Lists all available interactive commands. |
| `d` | **Detach** | Quits the `flutter run` process but keeps the app running on the emulator. |
| `q` | **Quit** | Stops the app and the `flutter run` process. |

## Troubleshooting

- **Device not found?**
  Run `flutter devices` to see listed devices. If the emulator isn't listed, try launching it again or run `adb devices` to check the Android Debug Bridge connection.

- **Build errors?**
  Run `flutter clean` then `flutter pub get` to reset your build environment.
