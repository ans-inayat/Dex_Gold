# Dex Gold

Dex Gold is a lightweight Android application that wraps a WebView to display a remote website. Designed to provide a seamless in-app browsing experience, the app supports deep links, file downloads, swipe-to-refresh functionality, and a splash screen. Ideal for turning responsive websites into mobile apps quickly and efficiently.

---

## 🌐 Live URL

The app loads content from:
**[`https://mintcream-termite-347286.hostingersite.com/`](https://mintcream-termite-347286.hostingersite.com/)**

---

## ✨ Features

* 📱 **WebView Wrapper** – Displays external web content inside the app.
* 📤 **File Download Support** – Automatically downloads files triggered from the webpage using Android's `DownloadManager`.
* 🔗 **Deep Linking** – Handles and opens specific paths directly within the WebView via verified HTTPS URLs.
* 🔄 **Swipe-to-Refresh** – Reload the current page with a pull gesture.
* 📶 **Network Connectivity Check** – Notifies the user when there’s no internet connection.
* 🎬 **Splash Screen** – Launch animation with delay before the main activity.
* 🧭 **Back Navigation** – Custom back behavior with exit confirmation.

---

## 🛠️ Permissions

Dex Gold uses the following permissions for core functionality:

```xml
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
<uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
<uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" tools:targetApi="31" />
```

> ⚠️ `WRITE_EXTERNAL_STORAGE` and `READ_EXTERNAL_STORAGE` are deprecated starting from Android 10 (API 29+). Consider using [Scoped Storage](https://developer.android.com/about/versions/10/privacy/changes#scoped-storage) for production apps.

---

## 🔗 Deep Link Support

Dex Gold responds to HTTPS links matching:

```
https://mintcream-termite-347286.hostingersite.com/*
```

### Example Intent Filter:

```xml
<intent-filter android:autoVerify="true">
    <action android:name="android.intent.action.VIEW" />
    <category android:name="android.intent.category.DEFAULT" />
    <category android:name="android.intent.category.BROWSABLE" />
    <data android:scheme="https" android:host="mintcream-termite-347286.hostingersite.com" android:pathPattern="/.*" />
</intent-filter>
```

---

## 📁 Project Structure

```
com.ff.flowfunding
├── MainActivity.java         # Main WebView activity
├── SplashActivity.java       # Launch screen with timed delay
├── CheckNetwork.java         # Utility to check for internet availability
├── res/layout                # Layout files including WebView and splash
├── AndroidManifest.xml       # App config, permissions, deep links
```

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/ans-inayat/Dex_Gold.git
```

### 2. Open in Android Studio

* Sync Gradle
* Connect device or start emulator
* Build and run the app

---

## ✅ Testing Scenarios

| Scenario               | Expected Behavior                  |
| ---------------------- | ---------------------------------- |
| No Internet            | Shows alert dialog                 |
| Pull to Refresh        | Reloads current page in WebView    |
| Open Downloadable Link | File gets downloaded automatically |
| Click Deep Link        | App opens and navigates to the URL |
| Back Button Press      | Navigates back or prompts to exit  |

---

## 📄 License

This project is licensed under the MIT License.
See the [LICENSE](https://github.com/ans-inayat/Dex_Gold/blob/main/LICENSE) file for details.

---

## 🙌 Contributing

Contributions, issues, and feature requests are welcome!
Feel free to fork the repo and submit a pull request.

---
