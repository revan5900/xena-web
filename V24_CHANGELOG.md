# v24 changelog

- Removed duplicate room leave route so the robust leave lifecycle is the only handler.
- Removed duplicate legacy moderation route; moderator-aware `/moderation` is authoritative.
- Room notifications are now pushed live to connected WebSocket clients.
- Room config now exposes seat mode and admin IDs.
- Removed duplicate legacy Ludo client functions.
- Added live notification badge handling when a badge element is present.
