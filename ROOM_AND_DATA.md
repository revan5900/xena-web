# Web-owned data

The web application uses its own namespace (`ureyimsen-web-v12` by default) and does not read runtime state from the APK.

New accounts start with:
- rating: 0
- coins: 0
- VIP: 0
- gift counters: 0
- followers/following: 0

Production note: `/api/wallet/recharge` is a development credit endpoint, not a real payment gateway. Replace it with a verified payment webhook before accepting real money.
