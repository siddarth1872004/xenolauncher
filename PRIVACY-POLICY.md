# Privacy Policy for Xeno — Minimal Launcher

**Last updated:** September 15, 2026

## Overview

Xeno ("the app") is a free, open-source Android launcher built on the principle of minimal data collection. This privacy policy describes what data the app collects, how it uses that data, and your rights regarding your privacy.

**TL;DR:** Xeno does not collect, transmit, or store any personal data on remote servers. All configuration, widget settings, home screen layouts, and preferences are stored locally on your device only.

---

## 1. What Data Does Xeno Collect?

### Local Data (Stored Only on Your Device)

Xeno stores the following data **entirely on your device** in its private application directory (`/data/data/com.xeno.launcher/`):

- **Home screen layout & configuration** — positions, sizes, rotations, and alignment of items and widgets you place
- **Widget settings** — configurations for Clock, Calendar, Habit counters, Timers, Notes, and other built-in widgets
- **User preferences** — theme choices, gesture settings, freeform editing toggles, icon pack selections, and visual customizations
- **App drawer state** — sorted app list, app labels, and folder assignments
- **Preset/backup exports** — snapshots of your entire launcher state, generated on-demand and stored locally (or exported to external storage if you choose to share them)

### Data NOT Collected

Xeno **does not**:
- Collect or transmit your personal information (name, email, phone number, location, etc.)
- Send analytics, crash reports, or telemetry to any remote server
- Track app usage, home screen activity, or widget interactions
- Require cloud sign-in or account creation
- Integrate with third-party advertising or tracking services
- Collect browsing history, contacts, calendar events, or other private data (even if widgets display such data, they fetch it directly from your device's local system services, not through Xeno)

---

## 2. Permissions Explained

Xeno requests the following Android permissions. Each is explained below:

| Permission | Why Needed |
|---|---|
| `QUERY_ALL_PACKAGES` (package visibility) | To populate the app drawer with installed apps and allow you to launch them. Required for the drawer's app search and filtering. |
| `CHANGE_CONFIGURATION` | To listen for system-wide configuration changes (e.g., theme changes, font size adjustments) so Xeno's UI can update accordingly. |
| `READ_CALENDAR` | **Optional**, only used if you place a Calendar widget. The widget reads your calendar directly from your device's calendar provider to display upcoming events. |
| `READ_CALL_LOG` | **Optional**, only used if you enable call-log display features. Reads call history only from your local device database. |
| `MANAGE_DEVICE_ADMINS` | Required for Xeno to act as a lock-screen alternative (if enabled). Does not grant access to other data. |
| `RECEIVE_BOOT_COMPLETED` | Allows Xeno to re-launch automatically when your device restarts, maintaining your home screen state. |
| `SYSTEM_ALERT_WINDOW` / `WRITE_SECURE_SETTINGS` | Used for advanced UI features (custom system-level integrations) if enabled. |
| `WRITE_EXTERNAL_STORAGE` | Only needed if you manually export a backup/preset to your device's Downloads folder or another external location. Xeno does not automatically write anywhere. |

All permissions are requested at runtime (Android 6.0+) and are optional for most features. If you deny a permission, Xeno will simply skip the associated feature.

---

## 3. Data Storage & Security

### Where Your Data Lives

- **On-device storage:** All configuration and user preferences are stored in Xeno's private application directory (`/data/data/com.xeno.launcher/`). Only Xeno can read and write to this directory.
- **Shared system data:** Calendar, contacts, and call logs are stored by Android's own system providers. Xeno reads from these only when you explicitly use a widget or feature that requires it.
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
- If a Calendar or Contacts widget is displayed, that data comes from your device's system providers, not from Xeno. Xeno only reads and displays it; it does not transmit it elsewhere.

### With Developers

- No personal data is sent to Xeno's developers or maintainers.
- If you report a bug via GitHub Issues or email, **only the information you voluntarily include** is shared; Xeno does not collect crash data automatically.

---

## 6. Data Retention

- **As long as you use Xeno:** All on-device configuration persists until you uninstall the app.
- **After uninstalling:** Your data is automatically deleted when you remove Xeno (standard Android behavior). The app has no residual data lingering on your device.
- **Backups you create:** Any manual backup/preset exports remain until you delete them. You are responsible for managing these files.

---

## 7. Your Rights & Choices

### Access & Export

You can export your entire home screen configuration, widget settings, and preferences as a backup file at any time (via **Freeform → Presets → Export**). This file can be imported on another device or kept as a record.

### Delete Your Data

All data associated with Xeno is deleted when you uninstall the app. There is no cloud account, no login, and no remote backup to delete separately.

### Opt-Out

- You can deny permissions at any time via **Settings → Apps → Xeno → Permissions**. Features relying on a denied permission will simply be unavailable.
- You can disable specific widgets or features in Xeno's settings.
- You can disable automatic launch-on-boot via **Freeform → Settings → System** (if available).

---

## 8. Changes to This Policy

We may update this privacy policy to reflect changes in the app or legal requirements. The "Last updated" date at the top of this document will always show the most recent revision. Significant changes will be announced in release notes.

Your continued use of Xeno after an update to this policy constitutes acceptance of the new terms.

---

## 9. Contact & Support

If you have questions about this privacy policy, wish to report a privacy concern, or want to clarify what data Xeno collects, please contact us:

- **GitHub Issues:** [xeno-launcher/issues](https://github.com/xenobuildssupport/xeno-launcher/issues)
- **Email:** xenobuildssupport@gmail.com

---

## 10. Compliance & Legal

This app is provided "as is" without any warranties. Xeno complies with:

- **Android Data Security & Privacy Requirements** — as mandated by Google Play
- **GDPR** (where applicable) — Xeno's minimal data collection and no cross-border transmission means GDPR implications are minimal
- **CCPA** (California Consumer Privacy Act) — Users in California have the right to know what data is collected and request deletion; Xeno's model (local-only storage) means you always own and control your data

No personal data is collected, stored remotely, or sold to third parties.

---

**Xeno is built on the principle that your phone, your data, your launcher.** We respect that principle in every design decision.
