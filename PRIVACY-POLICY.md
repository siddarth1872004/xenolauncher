# Privacy Policy for Xeno — Minimal Launcher

**Last updated:** September 28, 2026

## Overview

Xeno ("the app") is a paid, closed-source Android launcher built on the principle of minimal data collection. This privacy policy describes what data the app collects, how it uses that data, and your rights regarding your privacy.

**TL;DR:** Xeno does not collect, transmit, or store any personal data on remote servers. All configuration, widget settings, home screen layouts, and preferences are stored locally on your device only.

---

## 1. What Data Does Xeno Collect?

### Local Data (Stored Only on Your Device)

Xeno stores the following data **entirely on your device** in its private application directory (`/data/data/com.xeno.launcher/`):

- **Home screen layout & configuration** — positions, sizes, rotations, and alignment of items and widgets you place
- **Widget settings** — configurations for Clock, Calendar, Habit counters, Timers, Notes, and other built-in widgets
- **User preferences** — theme choices, gesture settings, freeform editing toggles, icon pack selections, and visual customizations
- **App drawer state** — sorted app list, app labels, and folder assignments, plus your last five drawer searches (turning Search history off also forgets them)
- **App lock & app timer settings** — which apps are locked and each timer's daily allowance
- **Preset/backup exports** — snapshots of your entire launcher state, generated on-demand and stored locally (or exported to external storage if you choose to share them)

### Data NOT Collected

Xeno **does not**:
- Collect or transmit your personal information (name, email, phone number, location, etc.)
- Send analytics, crash reports, or telemetry to any remote server
- Keep its own record of your app usage, home screen activity, or widget interactions (with Usage access granted, it reads Android's on-device usage totals for the features listed under `PACKAGE_USAGE_STATS` below, and keeps no log of its own)
- Require cloud sign-in or account creation
- Integrate with third-party advertising or tracking services
- Collect browsing history, contacts, calendar events, or other private data (even if widgets display such data, they fetch it directly from your device's local system services, not through Xeno)

---

## 2. Permissions Explained

Xeno requests the following Android permissions — this list is kept in
sync with the app's actual manifest, not a generic template:

| Permission | Why Needed |
|---|---|
| `QUERY_ALL_PACKAGES` | Xeno is a home screen replacement. Listing and launching your installed apps — the app drawer and home screen — cannot work without it. The list is never transmitted off your device. |
| `SET_WALLPAPER` | Only used if you choose Settings' "Set plain wallpaper" option, which replaces your wallpaper with a flat colour derived from your accent colour. |
| `ACCESS_NETWORK_STATE` / `ACCESS_WIFI_STATE` | Used only to show connectivity status where relevant (e.g., a Quick Settings-style toggle). No network requests are made using this. |
| `EXPAND_STATUS_BAR` | Lets a tap on the status bar area open the notification shade, matching standard Android home-screen behaviour. |
| `REQUEST_DELETE_PACKAGES` | Lets you uninstall an app directly from the app drawer's long-press menu, using Android's own uninstall confirmation dialog. |
| `SET_ALARM` (`com.android.alarm.permission.SET_ALARM`) | Used only if you tap Xeno's Clock widget/shortcut and choose to set an alarm — opens your device's own alarm app. |
| `KILL_BACKGROUND_PROCESSES` | Used only for the optional "clear background apps" gesture/shortcut, if you enable it. |
| `PACKAGE_USAGE_STATS` | **Optional.** Read on demand from Android's on-device usage stats for: your daily screen-time total, app timers (how long an app has been used today, against its allowance), and the app drawer's "Most used" sort and Recent row. Never stored or transmitted. These features are simply hidden or fall back to A–Z if you don't grant it. |
| `READ_CALENDAR` | **Optional**, only used if you place a Calendar widget. The widget reads your calendar directly from your device's calendar provider to display upcoming events. Never stored or transmitted; the widget shows nothing if you don't grant it. |
| `READ_CONTACTS` | **Optional**, off by default. Only if you turn on "Search contacts" (Settings › App drawer): the drawer's search box also matches your contacts by name, read on demand as you type. Never stored, indexed or transmitted. Not requested while the setting is off. |
| `READ_MEDIA_IMAGES` / `READ_MEDIA_VIDEO` / `READ_MEDIA_AUDIO` / `READ_MEDIA_VISUAL_USER_SELECTED` (Android 13+), `READ_EXTERNAL_STORAGE` (Android 12 and below) | **Optional**, off by default. Only if you turn on "Search files" (Settings › App drawer): the drawer's search box also matches the *names* of your photos, videos, music and downloads (at most five results). File contents are never read, and nothing is stored, indexed or transmitted. On Android 12 and below the same permission also lets the wallpaper filters read your current wallpaper to blur or tint it. Photos you pick for albums, icons or stickers go through Android's photo picker and need no permission. |
| `USE_BIOMETRIC` | **Optional.** Used only by App lock, to ask for your fingerprint, face or screen lock (Android's own prompt) before a locked app opens. Xeno never sees or stores biometric data. |

Three more permissions are requested as special access grants, not plain
manifest permissions, and only if you choose to use the features they power:

| Feature | What it needs |
|---|---|
| Double-tap-to-lock | Requests **Device Administrator** access, scoped to the lock-screen policy alone. Xeno performs no other device management and cannot wipe, encrypt, or otherwise manage your device. |
| Notification badges & media widget | Requests **Notification access**. Notification contents are read to show a badge dot, media-player controls, or the optional Notifications widget; they are kept in memory only while shown, never stored or transmitted. |
| Gesture system actions (Accessibility lock method) | **Optional**, off by default. Requests the **Accessibility service**, only after an in-app explanation you must accept, so a gesture you assign can lock the screen (keeping fingerprint unlock working), open recent apps, go back, show the power menu or take a screenshot. The service reads no screen content and receives no accessibility events; nothing is stored or transmitted. |

`QUERY_ALL_PACKAGES` and the plain install-time permissions above are
granted when you install Xeno. Everything marked optional, and the special
access grants, are asked for only when you turn on the feature that uses
them. If you deny one, Xeno simply skips that feature rather than failing.

---

## 3. Data Storage & Security

### Where Your Data Lives

- **On-device storage:** All configuration and user preferences are stored in Xeno's private application directory (`/data/data/com.xeno.launcher/`). Only Xeno can read and write to this directory.
- **Shared system data:** Calendar events and contacts are stored by Android's own system providers. Xeno reads from these only when you explicitly use a widget or feature that requires it.
- **Optional exports:** If you generate a backup/preset export, it is stored locally in the location you choose (e.g., Documents folder, Downloads, or an external SD card). You fully control when, where, and whether to create these exports.

### Encryption & Security

- Xeno stores its local data in the app's sandboxed directory with Android's built-in file permissions. No additional encryption is applied at the application level; Android's system-level encryption (if enabled on your device) protects all app data by default.
- Xeno does not transmit data over the internet, so there is no risk of interception during transmission.
- Sensitive configuration (like app shortcuts and widget settings) is never logged or exposed to other apps.

---

## 4. Third-Party Services

Xeno does **not** use any third-party analytics, crash-reporting, or tracking services. The app is entirely self-contained and communicates with Android system services only to:

- Query installed apps (via `PackageManager`)
- Read calendar data (via `CalendarProvider`, if you use a Calendar widget)
- Access system settings and themes

No data is sent to Google, Firebase, Mixpanel, or any other external service.

---

## 5. Sharing Data

### With Other Apps

- Xeno does not automatically share your data with other apps.
- If you explicitly create a backup/preset export and share it (e.g., via email or cloud storage), you are choosing to share that data. The file itself is not protected and can be read by any app you grant it to.
- If a Calendar widget or a contact search result is displayed, that data comes from your device's system providers, not from Xeno. Xeno only reads and displays it; it does not transmit it elsewhere.

### With Developers

- No personal data is sent to Xeno's developers or maintainers.
- If you report a bug or send feedback by email, **only the information you voluntarily include** is shared; Xeno does not collect crash data automatically.

---

## 6. Data Retention

- **As long as you use Xeno:** All on-device configuration persists until you uninstall the app.
- **After uninstalling:** Your data is automatically deleted when you remove Xeno (standard Android behavior). The app has no residual data lingering on your device.
- **Backups you create:** Any manual backup/preset exports remain until you delete them. You are responsible for managing these files.

---

## 7. Your Rights & Choices

### Access & Export

You can export your entire home screen configuration, widget settings, and preferences as a backup file at any time (via **Settings → Presets → Export**). This file can be imported on another device or kept as a record.

### Delete Your Data

All data associated with Xeno is deleted when you uninstall the app. There is no cloud account, no login, and no remote backup to delete separately.

### Opt-Out

- You can deny permissions at any time via your device's **Settings → Apps → Xeno → Permissions**. Features relying on a denied permission will simply be unavailable.
- You can remove any widget, or delete a folder or item, directly from the home screen at any time.
- You can pick your language (English, Spanish, French, German, or Hindi) at first setup or any time after, via **Settings → Appearance → Language**.

---

## 8. Changes to This Policy

We may update this privacy policy to reflect changes in the app or legal requirements. The "Last updated" date at the top of this document will always show the most recent revision. Significant changes will be announced in release notes.

Your continued use of Xeno after an update to this policy constitutes acceptance of the new terms.

---

## 9. Contact & Support

If you have questions about this privacy policy, wish to report a privacy concern, or want to clarify what data Xeno collects, please contact us:

- **Email:** xenobuildssupport@gmail.com

Xeno's source is closed (see "paid, closed-source" above), so there is no
public issue tracker for the app itself — email is the direct channel.
The GitHub repository hosting this policy page contains only this page's
own files, not the app's source.

---

## 10. Compliance & Legal

This app is provided "as is" without any warranties. Xeno complies with:

- **Android Data Security & Privacy Requirements** — as mandated by Google Play
- **GDPR** (where applicable) — Xeno's minimal data collection and no cross-border transmission means GDPR implications are minimal
- **CCPA** (California Consumer Privacy Act) — Users in California have the right to know what data is collected and request deletion; Xeno's model (local-only storage) means you always own and control your data

No personal data is collected, stored remotely, or sold to third parties.

---

**Xeno is built on the principle that your phone, your data, your launcher.** We respect that principle in every design decision.
