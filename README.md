# lp-dash

Revenue dashboard for the LP tools service fee. `collect.mjs` runs on GitHub
Actions every 3 hours, reads the fee payments from the explorer and chain RPC,
and writes `data/db.enc`, the whole database encrypted with the dashboard
password (AES-256-GCM, PBKDF2-SHA256). `index.html` asks for that password and
decrypts it in the browser. Repository secrets: `DASH_PASSWORD`, `FEE_WALLET`.

Run locally: `DASH_PASSWORD=... FEE_WALLET=0x... node collect.mjs`
