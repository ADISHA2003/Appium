# 📘 Appium + Real Device Setup (No Admin) — Notes

---

# 🔧 1. ADB (Android Device Bridge)

## 👉 Check connected devices

```bash
"C:\Users\212601\Downloads\platform-tools-latest-windows\platform-tools\adb.exe" devices
```

---

# ⚙️ 2. Set Environment Variables (Temporary – No Admin)

👉 Run in SAME CMD where Appium will run:

```bash
set ANDROID_HOME=C:\Users\212601\Downloads\platform-tools-latest-windows\platform-tools
set ANDROID_SDK_ROOT=C:\Users\212601\Downloads\platform-tools-latest-windows\platform-tools
```

---

## 🔁 Verify again:

```bash
"C:\Users\212601\Downloads\platform-tools-latest-windows\platform-tools\adb.exe" devices
```

---

# 🚀 3. Start Appium Server

```bash
appium
```

👉 Keep this running

---

# 📱 4. Device Requirements

* USB Debugging → ON
* Device connected via USB
* Device unlocked
* Authorized for debugging

---

# 🧩 5. Desired Capabilities (Appium Inspector / Code)

```json
{
  "platformName": "Android",
  "appium:automationName": "UiAutomator2",
  "appium:deviceName": "Android",
  "appium:udid": "8TCAZLO7758L6DDQ",
  "appium:appPackage": "com.android.settings",
  "appium:appActivity": ".Settings",
  "appium:noReset": true
}
```

---

# 🧠 6. Important Capabilities Explained

* `platformName` → Android platform
* `automationName` → UiAutomator2 driver
* `deviceName` → generic name
* `udid` → unique device ID (from adb)
* `appPackage` → app identifier
* `appActivity` → launch screen
* `noReset=true` → prevents app data reset (important for system apps)

---

# ⚠️ 7. Common Issues + Fix

## ❌ Device not found

👉 Run:

```bash
adb devices
```

---

## ❌ ANDROID_HOME not set

👉 Fix using:

```bash
set ANDROID_HOME=...
```

---

## ❌ Permission error (system apps)

👉 Use:

```json
"appium:noReset": true
```

---

## ❌ Appium not detecting device

👉 Ensure:

* Same CMD for env + appium
* Device unlocked
* USB debugging allowed

---

# 🔥 8. Flow Summary (End-to-End)

```text
ADB → Set ENV → Start Appium → Connect Device → Run Session
```
---
