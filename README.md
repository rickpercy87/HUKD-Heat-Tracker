# HUKD Heat Tracker

Native Android app that monitors HotUKDeals deal temperatures and highlights fast-rising deals.

## What it does

- Polls roughly every 15 minutes with Android WorkManager.
- Adds newly discovered deals automatically.
- Stores deal and temperature history locally in SQLite.
- Calculates current temperature, recent change and approximate degrees/hour.
- Sorts by fastest-rising, hottest, newest, or biggest recent gain.
- Includes manual refresh, search and filters.

## Build

The GitHub Actions workflow in this repository reconstructs the Android Studio project from `android-project.zip.b64`, builds a debug APK, and uploads it as an Actions artifact named `HUKD-Heat-Tracker-APK`.

The source archive expands to the `HUKDHeatTrackerAndroid` project directory.

## Notes

Android periodic WorkManager jobs have a 15-minute minimum interval and may be deferred by Android battery/Doze scheduling. HUKD network/API behaviour can also change, so the app records fetch errors rather than retrying aggressively.
