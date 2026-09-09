# v25

- Fixed phantom-room creation in seat/admin/moderation/message routes.
- Closed/nonexistent rooms now return 404 instead of being created implicitly.
- API config version and default PostgreSQL namespace updated to v25.
- Preserved prior room, seat-request, moderation, gifts, PK, Ludo, auth and WebSocket work.
