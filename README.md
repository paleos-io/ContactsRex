# Contacts Rex

A local-first address book for Android, by [PALEOS.IO](https://paleos.io ). Find, organize, and move your contacts without a required cloud account.

**Offline by default. No ads. No tracking.**

## Features

- Search names, numbers, and contact details.
- Organize contacts with favorites and groups.
- Keep private contacts in encrypted, app-owned storage.
- Import and export standard vCard (`.vcf`) files.
- Choose visible fields, Light / Dark / AMOLED themes, fonts, and text size.
- Block screenshots; optionally restrict overlays on Android 12 and later.

## Privacy boundaries

The app has [no `INTERNET` permission](app/src/main/AndroidManifest.xml). Contacts saved to Android's system address book may still sync through accounts configured on your device. Contacts Rex does not control those account settings.

Private contacts use [SQLCipher-backed storage](patched-fossify-commons/commons/src/main/kotlin/org/fossify/commons/databases/ContactsDatabase.kt), with the database key protected through [Android Keystore](patched-fossify-commons/commons/src/main/kotlin/org/fossify/commons/helpers/SqlCipherKeyManager.kt). This encryption does not cover Android system contacts or exported vCard files. Screen protections are Android window controls, not an absolute guarantee against capture.

Export a separately protected vCard before clearing app data, uninstalling, or resetting your device. The encrypted private database depends on the device's Keystore key. vCard exports are plaintext contact files, not encrypted or complete app backups.

## Install

Android 10 or later. Install the signed APK from this repository's Releases page. Contacts permission is needed to work with Android's system address book.

Package: `io.paleos.contactsrex`.
Keep production signing keys, credential records, and private recovery archives out of public repositories and release assets.

