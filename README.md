# pegala

A simple Flutter WebView application.

## Getting Started

This directory contains the source code for a Flutter application that loads `https://pegala.tv.br/indexapp.html` via WebView, along with a simple Splash Screen.

### Setup Instructions

1.  Make sure you have [Flutter installed](https://docs.flutter.dev/get-started/install).
2.  Navigate to this directory (`meu_webview_app`) in your terminal or CI environment.
3.  Run the following command to generate the native project structures (like the `ios` and `android` folders):
    ```bash
    flutter create .
    ```
4.  Fetch dependencies:
    ```bash
    flutter pub get
    ```

### iOS Specific Configuration

The `webview_flutter` package requires a minimum deployment target of iOS 11.0 or higher.
After running `flutter create .`, you may need to adjust your `ios/Podfile`:

1.  Open `ios/Podfile`.
2.  Uncomment and change the platform line to at least iOS 11.0:
    ```ruby
    platform :ios, '11.0'
    ```
3.  Install the iOS pods (this is usually done automatically by flutter build, but you can force it):
    ```bash
    cd ios
    pod install
    cd ..
    ```

### Building for iOS

To build the iOS app (requires a Mac with Xcode installed or a macOS runner in GitHub Actions):
```bash
flutter build ios --release --no-codesign
```

Note: If you're using GitHub Actions, ensure your workflow includes steps to install Flutter, set up Xcode, and handle iOS code signing if necessary.
