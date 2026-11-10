# TCL Cinematic Launcher — cloud-build starter

This project targets Android 11+ TV devices and is designed around the supplied TCL 43U61 information (1080p, 2 GB RAM). It is a starter, not a finished Apple TV clone.

## Build without Android Studio using GitHub Actions
1. Create a GitHub account if needed.
2. Create a new **private** repository.
3. Upload the contents of this ZIP to the repository root (not the ZIP file itself).
4. Open the repository's **Actions** tab.
5. Select **Build TCL Cinematic APK**, then **Run workflow**.
6. When complete, open the successful run and download the `TCL-Cinematic-debug` artifact.
7. Extract the artifact; it contains `app-debug.apk`.

GitHub account and Actions usage are subject to GitHub's current plan/usage limits. This requires a few browser steps; no Android Studio is needed.

## Install
Connect TV and PC to the same hotspot, confirm `adb devices` shows the TV, then:
`adb install -r app-debug.apk`

Do not disable the existing Google TV or TCL launcher. When Android asks which Home app to use, select TCL Cinematic for **Just once** first. Test Back, Home, D-pad and app launching before considering a default launcher.

## TMDB
Use the TMDB **API Read Access Token**, not the shorter API key, in the app. The app stores it in private app preferences and calls `/3/movie/popular` with Bearer authentication. Do not paste the token into source code or send it in chat.

TMDB attribution and logo requirements must be met before distribution. This app is not endorsed or certified by TMDB.

## Current limitations
- Movie rows currently show text titles and ratings; poster images, cinematic hero art, continue-watching and rich detail screens are not implemented yet.
- The app is not yet compiled or device-tested. The GitHub Actions workflow builds a debug APK but does not guarantee TCL-specific runtime compatibility.
- No system packages are modified by installing this APK.
