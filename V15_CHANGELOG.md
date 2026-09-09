# v15 changes
- Web namespace default is now `ureyimsen-web-v15`.
- PK start validates the opponent is in the room and prevents duplicate active PKs.
- PK score can only be added by the participant on the matching side; expired PKs are closed automatically when scored.
- Ludo cannot be reset by a non-owner while a game is waiting/active.
- Players cannot join an ended Ludo game.
- Existing APK assets remain bundled only as static resources; the Web runtime does not launch or depend on the APK.
