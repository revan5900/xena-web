# v23

- Fixed duplicate `/api/rooms/:id/messages` route so room membership is always enforced.
- Fixed profile update response so `passwordHash` is never returned.
- Added lightweight IP-based rate limits to guest/register/login endpoints.
- Updated API namespace/config version to v23.
- Preserved v22 room leave, seat request, moderation, PK, gifts, Ludo, WebSocket and Railway support.
