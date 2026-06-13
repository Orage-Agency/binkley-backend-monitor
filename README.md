# binkley-backend-monitor

External uptime monitor for the OKC Onsite Detailing voice-agent backend ("Olivia").

The n8n backend runs on a PC behind a Cloudflare tunnel (`n8n-binkley.orage.agency`).
If that PC is off or the tunnel drops, Olivia's booking tools stop working. This
GitHub Action runs on GitHub's servers — independent of the PC — pings the health
endpoint every 5 minutes, and sends an SMS alert if it's unreachable.

No secrets live in this repo. All config is in encrypted GitHub Actions secrets:
`HEALTH_URL`, `TWILIO_ACCOUNT_SID`, `TWILIO_AUTH_TOKEN`, `TWILIO_MGS`, `ALERT_TO`.

Manual test: Actions tab → binkley-backend-monitor → Run workflow.
