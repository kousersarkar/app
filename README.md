# Build the APK
## Option A: GitHub (no installs)
1. Create a new GitHub repo and upload everything in this folder.
2. Open the Actions tab, run "Build APK" (it also runs on every push).
3. Download `app-debug.apk` from the run's Artifacts and install it on your phone.
## Option B: Locally (needs Node 18+, JDK 17, Android SDK)
npm install && npx cap add android && npx cap sync android
cd android && ./gradlew assembleDebug
APK: android/app/build/outputs/apk/debug/app-debug.apk
Or run `npx cap open android` and use Build > Build APK in Android Studio.
## Notes
- Change appId in capacitor.config.json before publishing to Play Store.
- Play Store needs a signed release build (AAB) - debug APKs are for sideloading.
- Edit the app in www/index.html, then `npx cap sync android`.
