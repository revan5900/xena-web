# Railway deployment

1. Create a Railway project and deploy this repository/ZIP contents.
2. Railway automatically supplies `PORT`; the server listens on `0.0.0.0`.
3. Add a PostgreSQL service for production persistence. The current build still supports `DB_FILE` for development, but Railway's normal container filesystem should not be treated as permanent storage.
4. Set `CORS_ORIGINS` to `https://ureyimsen.com,https://www.ureyimsen.com`.
5. Generate a Railway public domain. The WebSocket endpoint is the same host using `wss://`.
6. Point `ureyimsen.com` DNS to the Railway-provided custom-domain target and enable HTTPS in Railway.
7. For production WebRTC, configure a TURN server with `TURN_URL`, `TURN_USERNAME`, and `TURN_CREDENTIAL`; STUN alone is not sufficient for every mobile network.
8. Health check: `/health`. Railway status check: `/api/railway-status`.

Important: this project does not contain any Railway password, API token, database password, or private credential. Put secrets in Railway Variables.

## Production media
The browser WebRTC layer is signaling through the app, but a real multi-user live room still needs an SFU/TURN service. Set `TURN_URL`, `TURN_USERNAME`, and `TURN_CREDENTIAL` for TURN. For production video/audio, deploy a self-hosted WebRTC SFU (for example LiveKit or mediasoup) as a separate Railway service and connect its token endpoint to this app. Do not put provider secrets in the frontend.

## Authentication
The web build now supports email/password registration and login using Node `scrypt` password hashing, in addition to guest sessions.

## Fresh web data
Set `APP_NAMESPACE=ureyimsen-web-v26`. PostgreSQL data is stored under this namespace, so this Web app stays separate from older deployments. New accounts begin at rating 0, VIP 0 and coin balance 0.

Keep `ALLOW_DEV_RECHARGE` unset in production. The development recharge endpoint and buttons are disabled unless it is exactly `true`.

## Optional SFU
The server includes a `/api/livekit/token` endpoint. If you deploy your own LiveKit SFU as a separate Railway service, set `LIVEKIT_URL`, `LIVEKIT_API_KEY`, and `LIVEKIT_API_SECRET`; secrets stay server-side. The current browser mesh remains the fallback when LiveKit is not configured.
