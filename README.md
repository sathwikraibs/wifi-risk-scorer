# SafeHop — Wi-Fi Security Scanner

SafeHop checks how safe your current internet connection is. It looks at your IP, VPN status, ISP, HTTPS, DNS privacy, region, and a handful of other signals, then gives you a risk score, a security grade, and a step-by-step guide to fix whatever it finds.

**Live site:** [safehop.vercel.app](https://safehop.vercel.app/)

## What it does

- **Auto-scan** — instantly detects your IP, location, ISP, and connection security signals
- **Manual scan** — check the risk of any IP address or domain
- **Risk score (0–100)** with a Safe / Moderate / Dangerous rating and letter grade (A+ to F)
- **8 security checks** — HTTPS, VPN, region safety, ISP type, proxy/datacenter detection, DNS privacy, IP exposure, protocol security
- **Personalized protection guide** — prioritized steps based on what your scan finds
- **Scan history & global stats** — tracks total scans, safe vs. risky, and average risk

## Tech stack

- **Backend:** Flask (Python)
- **Frontend:** Vanilla HTML/CSS/JS, Chart.js
- **Storage:** SQLite (local), optional Firebase Firestore for persistent stats
- **Hosting:** Vercel

## Project structure

```
safehop/
├── app.py                 # Flask app, scoring logic, API routes
├── requirements.txt       # Python dependencies
└── templates/
    └── index.html          # Frontend UI
```

## Running locally

```bash
pip install -r requirements.txt
python app.py
```

Then open `http://localhost:5000`.

## Deploying

Deployed on [Vercel](https://vercel.com) using its native Flask support — no extra config needed. Just import the repo and deploy.

Optional: set a `FIREBASE_KEY` environment variable (Firebase service account JSON) to persist scan stats across deployments. Without it, SafeHop falls back to a local SQLite database.

## Disclaimer

SafeHop gives a general risk estimate based on publicly available network signals. It isn't a substitute for a full security audit — always use a VPN and HTTPS on public networks regardless of the score shown.
