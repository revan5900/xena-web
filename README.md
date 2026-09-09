# Ureyimsen Live Web v26 — browser reconstruction

This project is a self-hostable browser implementation based on functionality evidenced in `xena-live-2-3-3-1.apk`.

## Included functional modules
- guest account/profile + editable profile
- live room discovery and creation (video/audio)
- 12-seat room layout, join/leave, chat, seat locks, microphone and moderation controls
- room announcement, cover/tags data, direct permitted audio player and admin panel
- browser microphone/camera capture
- WebSocket room realtime events and WebRTC signaling channel
- gift catalog, coin wallet, transactions and gift combo quantity
- gift animation hooks mapped to APK asset names
- PK invite/accept/decline/score/end
- red-envelope create/claim flow with wallet and duplicate-claim protection
- Moments create/like/feed
- follow/notification primitives
- VIP levels and purchase simulation
- ranking
- private-link/call signaling API
- Ludo classic/2v2 room, join/leave/reset/turn/dice API foundation
- CORS/allowed origin for `ureyimsen.com`
- original APK assets copied into `public/assets`

## Run
`npm install`
`npm start`

Open `http://localhost:8080`.

For production set `PORT`, `DATABASE_URL`, `APP_NAMESPACE`, and `CORS_ORIGINS`.

## Important
This is a functional web reconstruction, not a binary conversion of Android. Android-only Zego/beauty/PAG/SVGA behavior cannot run directly in a browser. Gift effects therefore have a CSS/emoji fallback, while production audio/video requires TURN or an SFU and real payments require a payment provider.

`POST /api/wallet/recharge` is disabled by default. It is only available when `ALLOW_DEV_RECHARGE=true` is deliberately set for a test deployment.

## Bu versiyada əlavə edilənlər
- Authorization Bearer yoxlaması (wallet/VIP/profile/gift əməliyyatları).
- WebSocket WebRTC siqnalları artıq konkret `to` istifadəçisinə yönləndirilir.
- Ludo növbə yoxlaması, 1-6 zar, çıxış (6), gediş və qalib vəziyyəti.
- Ludo üçün ayrıca `POST /api/ludo/:roomId/move` endpoint-i.
- `ureyimsen.com` CORS default olaraq aktivdir.

Qeyd: APK-dəki Zego/PAG/SVGA native komponentlərinin brauzer ekvivalenti ayrıca media/animasiya inteqrasiyası tələb edir; bu paket onları saxta şəkildə `100% native` kimi təqdim etmir.
