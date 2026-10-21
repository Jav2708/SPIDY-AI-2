SPIDY AI — Android Studio Project

This is the Android app source project wrapping the SPIDY AI mobile demo in a native Android WebView shell. It is not a precompiled APK.

Build an APK:
1. Install Android Studio on a computer: https://developer.android.com/studio
2. Extract this ZIP.
3. In Android Studio choose Open, then select the SPIDYAI project folder.
4. Allow Gradle sync and install Android SDK Platform 35 if prompted.
5. Use Build > Build Bundle(s) / APK(s) > Build APK(s).
6. The debug APK is normally at app/build/outputs/apk/debug/app-debug.apk.
7. Transfer that APK to your Android phone and install it. Android may ask you to allow installs from that source.

Notes:
- This project requires an internet connection for Gradle dependency/plugin setup.
- Voice features depend on browser/WebView speech API support and Android microphone permission.
- The bundled demo is a frontend. A secure backend/API connection is needed for full AI responses; do not embed private API keys in the APK.
- Package ID: com.spidyai.mobile
