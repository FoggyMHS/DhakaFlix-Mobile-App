DhakaFlix Mobile

A mobile-first Android application for browsing and streaming media from supported local ISP FTP/HTTP servers in Bangladesh.

DhakaFlix brings a familiar streaming-app experience to your Android phone, with a dark Netflix-inspired interface, featured content, searchable media libraries, and convenient playback controls.

Features

- 📱 Mobile-first Android interface
- 🎬 Netflix-inspired dark design
- 🏠 Featured content and horizontal media shelves
- 🔎 Media search
- 📺 Movie and TV series browsing
- ▶️ In-app media playback
- 🎞️ VLC player option
- 📂 Support for configured local FTP/HTTP media directories
- ⚙️ Customizable settings
- 💾 Watch progress support

Screens and navigation

The application includes:

- Home
- Movies
- Series
- Search
- Settings and About

Requirements

- Android 7.0 (API 24) or newer
- Internet or access to your ISP's local media server
- Android Studio or GitHub Actions for building

Installation

1. Download the latest APK from the GitHub Releases section.
2. Open the APK on your Android device.
3. Allow installation from your chosen file source if Android asks.
4. Install and launch DhakaFlix.

Configure media sources

DhakaFlix uses configured media directory URLs.

To change the available media sources:

1. Open "app/src/main/java/com/maibgoat/dhakaflix/Data.kt".
2. Locate the "CATEGORIES" configuration.
3. Update the directory URLs to the media folders available on your ISP network.
4. Rebuild the application.

Some ISP media servers use HTTP instead of HTTPS. The application currently permits cleartext HTTP connections for compatibility.

Build from source

Requirements

- JDK 17
- Android SDK 35
- Gradle 8.11.1

Build a debug APK

From the repository root:

gradle assembleDebug

The APK will be generated at:

app/build/outputs/apk/debug/app-debug.apk

Build using GitHub Actions

You can build DhakaFlix directly through GitHub without a computer.

1. Fork or upload this repository to GitHub.
2. Open the repository's Settings → Secrets and variables → Actions.
3. Add the following repository secrets:

Secret| Value
"SIGNING_KEY_BASE64"| Base64-encoded release keystore
"SIGNING_STORE_PASSWORD"| Keystore password
"SIGNING_KEY_ALIAS"| "maibgoat"
"SIGNING_KEY_PASSWORD"| Private key password

4. Open the Actions tab.
5. Select Build signed release.
6. Press Run workflow.
7. Wait for the build to finish.
8. Open the completed workflow run and download its APK artifact.

Generate the Base64 keystore value

On Linux or Termux:

base64 DhakaFlix-MAiB-GOAT-release.jks | tr -d '\n'

Copy the output into the "SIGNING_KEY_BASE64" secret.

Never upload your keystore or passwords to the public repository.

Publishing updates

To release a new version:

1. Make your changes.
2. Increase "versionCode" in "app/build.gradle.kts".
3. Update "versionName".
4. Push the changes to GitHub.
5. Run the GitHub Actions release workflow.
6. Download and publish the resulting APK in GitHub Releases.

Always use the same package ID and signing key for future updates.

Keep multiple secure backups of your release keystore. Losing it can prevent you from publishing compatible updates.

Application identity

- Application: DhakaFlix
- Publisher credit: MAiB_GOAT
- Package ID: "com.maibgoat.dhakaflix"

License and attribution

See the repository's "LICENSE" file for applicable licensing terms.

This project builds upon the original DhakaFlix project. Original authors' copyright and licensing terms must be respected. The right to redistribute and relicense the original code must be confirmed before public distribution.

---

Made with ❤️ by MAiB_GOAT