# Xena Web — Standalone Runtime

This Web project runs as its own Node.js/Express/WebSocket application. The browser does not launch the Android APK, call APK activities, or require the APK to be installed. Railway serves the Web app and its own API/WebSocket endpoints.

## Important rights note
The Web runtime being technically independent does **not** by itself transfer intellectual-property rights in artwork, animations, sounds, trademarks, or other assets copied from an APK. If an asset came from a third-party app, replace it with an asset you own or have permission to use before commercial/public deployment.

## Domain
Set `CORS_ORIGINS=https://ureyimsen.com,https://www.ureyimsen.com` in Railway.

## Data ownership boundary
The web application has its own database namespace (`APP_NAMESPACE`) and its own user, room, wallet, ranking, gift, PK and Ludo state. It does not call the APK at runtime. APK-derived assets bundled in `public/assets` are static files only; they are not an Android runtime dependency.
