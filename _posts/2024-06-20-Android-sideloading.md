---
layout: post
title: Android Sideloading Guide
subtitle: Deploy APKs directly without the Play Store
tags: [android, mobile, dev]
comments: true
---

Sideloading lets you install and test APKs directly on a device — no app store, no review process.

## Enable Developer Options

1. Go to **Settings → About phone**
2. Tap **Build number** 7 times
3. Developer Options will appear in Settings

## Allow Unknown Sources

In **Settings → Security**, enable **Install unknown apps** for the source you'll use (Files, ADB, etc.).

## Install via ADB

```bash
adb install path/to/your.apk
```

Useful flags:

```bash
adb install -r app.apk     # replace existing
adb install -d app.apk     # allow version downgrade
adb install -t app.apk     # allow test APK
```

## Check installed packages

```bash
adb shell pm list packages | grep yourapp
```

## Uninstall

```bash
adb uninstall com.example.yourapp
```

{: .box-warning}
**Warning:** Only sideload APKs from sources you trust completely.
