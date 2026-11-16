# Spend-Wisely

**Thoughtfully built by Pranav Patel to solve everyday problems.**

Spend-Wisely is an Android app for keeping track of everyday expenses in rupees. Add purchases as you make them, review your daily and monthly totals, and export a CSV when you need a spreadsheet.

[Download the APK from GitHub Releases](https://github.com/MRPRANAVPATEL/Spend-Wisely/releases/latest)

## Features

- **Manual expense entry** lets you add, edit, label, and delete purchases.
- **Spending dashboard** shows today’s total and expenses for the month you select. Search by the person or business you paid or by expense type.
- **SMS detection** identifies supported bank debit and UPI alerts using configurable senders and keywords. Matching transactions appear as pending expenses for you to review.
- **Reminders** prompt you to add details to pending expenses.
- **CSV export** lets you save or share a selected month or your full expense history.

## Install and get started

> Built for personal use and Android development practice. Install it at your own discretion.

1. On the latest release page, find `app-debug.apk` under **Assets**.
2. Open the APK on a phone running **Android 10 or later** and follow Android’s installation prompts.
3. Open **Expense Tracker** from the launcher, enter your name, and tap **Add expense** to record your first purchase.

The APK from GitHub Actions is debug-signed. Android requires a matching signing key for in-place updates. If you need to uninstall an existing copy before switching builds, export a CSV first to keep a copy of your records.

## SMS detection and privacy

Manual entry is available without SMS access. For automatic detection, open **Settings & setup**, grant SMS access, and review the sender and keyword lists. Tap **Add details** on a detected payment to label it and include it in your totals.

| Android access | Purpose |
| --- | --- |
| SMS | Checks incoming messages for supported debit and UPI alerts. |
| Notifications | Shows prompts and reminders for expenses waiting for details. |
| Appear on top and full-screen notifications | Lets a prompt appear over another app or on the lock screen when Android allows it. |

Expense records are stored on the phone in a Room database. SMS processing runs on the device. When you choose **Export CSV**, you can save the file through Android’s file picker or share it with another app.

## Build from source

| Area | Technology |
| --- | --- |
| Language | Kotlin 1.9.24 |
| UI | Jetpack Compose and Material 3 |
| Local data | Room and Preferences DataStore |
| Reminders | WorkManager |
| Build tools | Java 17, Gradle 8.7, and Android Gradle Plugin 8.5.2 |
| Android SDK | Compile and target API 34. Minimum API 29. |

Install a JDK 17, Gradle 8.7, and Android SDK Platform 34 with Build Tools 34.0.0. Set `JAVA_HOME` and `ANDROID_HOME`, then run the commands from the repository root.

```sh
gradle testDebugUnitTest assembleDebug
```

The debug APK is written to `app/build/outputs/apk/debug/app-debug.apk`.

## GitHub Actions

[Build APK](https://github.com/MRPRANAVPATEL/Spend-Wisely/actions/workflows/build-apk.yml) runs on each push and can also be started with **Run workflow**. It runs the SMS parser unit tests and builds the debug APK. A successful run uploads the `app-debug-apk` artifact and publishes a numbered GitHub Release with `app-debug.apk` attached.

---

*Thoughtfully built by Pranav Patel to make everyday expense tracking easier.*
