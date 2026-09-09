# Web room lifecycle

The Web version owns its own room state. Rooms can be created, joined, moderated, transferred to another host, and closed without reading state from the APK.

Production notes:
- Use PostgreSQL on Railway via `DATABASE_URL`.
- Set `APP_NAMESPACE=ureyimsen-web-production` once the production database is ready.
- Configure a real payment provider before enabling paid coin recharge.
- Configure LiveKit/TURN for scalable live media; mesh remains the fallback.
