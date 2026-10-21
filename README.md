# SPIDY AI Android — starter project

Features included:
- Spider/neon dark interface
- Hindi speech input (Android speech service) and text-to-speech replies
- Voice/text commands to open YouTube, WhatsApp, Settings
- Google web search
- Optional HTTPS AI-backend connection (POST JSON `{"message":"..."}`; expects JSON `{"reply":"..."}`)

## Important: AI backend
The Android app intentionally does **not** contain an AI provider API key. Keys embedded in APKs can be extracted. Deploy a small HTTPS backend that accepts `{"message":"..."}`, calls your chosen AI provider privately, and returns `{"reply":"..."}`. Paste that backend URL using the gear button in the app.

## Build APK (computer)
1. Install Android Studio from the official Android developer site.
2. Extract this ZIP.
3. Open the `SPIDY_AI_Android` folder in Android Studio.
4. Let Gradle sync and install the Android SDK requested by Android Studio if prompted.
5. Connect your Android phone with USB debugging enabled, or use an emulator.
6. Choose **Build > Build Bundle(s) / APK(s) > Build APK(s)**.
7. When complete, the debug APK is at `app/build/outputs/apk/debug/app-debug.apk`.
8. Copy the APK to your phone, tap it, and allow installation from that source if Android asks.

For a shareable signed APK, use **Build > Generate Signed Bundle / APK > APK** and create/keep your own keystore safely.

## Example backend contract
Request:
```json
{"message":"Explain photosynthesis in simple Hindi"}
```
Response:
```json
{"reply":"Photosynthesis is the process by which plants..."}
```

Use HTTPS only. Validate requests and apply rate limits on your backend. Do not expose provider API keys to the mobile app.

## Current limitations
- Voice recognition depends on the phone's installed speech-recognition service and network availability.
- Voice input is configured for Hindi (hi-IN); English text commands also work. You can change `hi-IN` in `MainActivity.kt` to `en-US` or add a language selector.
- AI chat requires a backend URL. Without one, app-opening and search commands work but general questions show setup instructions.
- This is a starter implementation, not yet tested on your particular phone.
