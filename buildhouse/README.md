# buildhouse

A small platform of self-contained web tools. Each app is plain HTML/CSS/JS in its own folder, with no build step and no server — so every tool runs straight from a file and works offline.

## Live structure

```
buildhouse/
├── index.html        → landing page (links to every app)
├── README.md
├── .gitignore
└── noted/
    └── index.html    → Noted — a personal perfume-note guide
```

When hosted, this maps to:

- `/`        → the landing page
- `/noted/`  → the Noted app

## Apps

**Noted** (`/noted/`) — Map the perfume notes you love and avoid, check any bottle against your profile for a 0–100 match score, and keep a list of your favourite fragrances. Fully offline; your custom profile is saved in the browser on each device.

## Run it locally

No tools needed. Just open `index.html` (or `noted/index.html`) in any browser.

## Deploy it (free)

Pick one and point your domain at it:

1. **GitHub Pages** — Repo *Settings → Pages → Deploy from branch → `main` / root*. Your site goes live at `https://rob7850.github.io/buildhouse/`.
2. **Cloudflare Pages / Netlify / Vercel** — Connect this repo; they auto-deploy on every push. Then add your custom domain in their dashboard.

To use a custom domain (e.g. `buildhouse.xyz`), add it in the host's dashboard and update the DNS at your registrar as they instruct.

## Add a new app

1. Create a folder: `your-app/`
2. Put your app in `your-app/index.html`
3. Add a card linking to `./your-app/` in the root `index.html`

That's it — the platform grows one folder at a time.

## Notes

- Everything is static and dependency-free (no npm, no frameworks), which keeps it fast, free to host, and offline-capable.
- Noted stores its custom profile in the browser's local storage, so it's per-device today. Cross-device sync would need a small backend (e.g. Supabase or Firebase) — a future step, not needed now.
