# Budget Manager

A self-hosted, single-household bill and budget manager.

- Track recurring bills with flexible splitting across paychecks (fixed or percentage, configurable number of paychecks).
- Frequencies: weekly, biweekly, semi-monthly, monthly, quarterly, semi-annual, yearly, one-time.
- Debts with auto-deducting balances, savings goals with progress, and per-period overrides.
- Bill-pay mode with a balance tracker.
- One shared database on the host (PGlite / Postgres-in-WASM), so every device sees the same data.
- Gated by WebAuthn passkeys (e.g. a YubiKey). Pairs well with a Cloudflare Tunnel for HTTPS on your own subdomain.

## Setup

1. Set **Public hostname** and **Public origin** to the domain you'll reach it at (e.g. your Cloudflare Tunnel subdomain). Passkeys are bound to this hostname.
2. Set a temporary **Registration secret**, install, then open the app and enroll your passkey using that secret. Afterwards clear the secret and update the app so no one else can enroll.
3. Sign in with your passkey. Data persists in the app's data volume.
