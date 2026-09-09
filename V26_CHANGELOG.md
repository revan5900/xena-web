# v26

- Fixed the seat-mode crash caused by an undeclared `mode` value.
- Fixed undeclared moderation and message variables.
- Prevented update/settings routes from creating phantom rooms.
- Added safe migration defaults for older room data.
- Added room announcement, cover/tags and permitted direct-audio metadata.
- Added room admin view, seat locks, microphone mute state and kick history.
- Added red envelopes with wallet debit/credit, expiry and duplicate-claim protection.
- Changed PK to invitation → accept/decline → active flow; added cancel support.
- Added Ludo classic/2v2 mode selection, leave and owner reset.
- Removed duplicate frontend handlers and the duplicate chat loader.
- Added browser-safe gift animation fallback and room audio controls.
- Disabled development coin recharge by default.
- Fixed Docker installation when no package lock is supplied.

Android-only Zego beauty filters and native PAG/SVGA runtimes are not claimed as browser features. Production media still needs TURN/SFU configuration.
