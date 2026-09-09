# v22
- Added explicit room leave endpoint so viewers can leave cleanly without waiting for WebSocket disconnect.
- Leave removes the viewer's seats and pending seat request, then broadcasts presence.
- Added `tests/smoke.js` covering health, guest auth, room creation/join, seat request/approval and leave.
- Kept the previous moderation, seat-mode, gift idempotency and WebSocket fixes.
