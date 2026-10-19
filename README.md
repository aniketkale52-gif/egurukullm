# eGurukul Web

Desktop web app for eGurukul (NEET PG / INICET prep). Plain HTML, CSS and JavaScript — no framework and no build step.

## Folder structure

```
egurukul-web/
├── index.html            App shell (header, sidebar, main area, AI Guru panel, modal)
├── assets/
│   ├── css/styles.css    All styles (light + dark theme tokens at the top)
│   ├── js/app.js         All screens, data and interactions
│   └── img/              Video thumbnails and schedule images
├── vercel.json           Vercel config (static site, caching headers)
├── package.json          Optional local preview script
└── .gitignore
```

## Run locally

Open the folder in Cursor and run:

```
npm run dev
```

Then open http://localhost:3000. (Or just open `index.html` in a browser.)

## Push to GitHub

```
git init
git add .
git commit -m "eGurukul web app"
git branch -M main
git remote add origin https://github.com/<your-username>/egurukul-web.git
git push -u origin main
```

## Deploy on Vercel

1. In Vercel, click **Add New → Project** and import the GitHub repo.
2. Framework preset: **Other**. Leave Build Command and Output Directory empty (the site is served from the repo root).
3. Click **Deploy**.

Every push to `main` redeploys automatically.

## How the app works

- Pages are switched with the URL hash, for example `/#qbank`, `/#tests`, `/#account`, `/#subs`, `/#schedule`.
- Progress, bookmarks, profile and settings are saved in the browser's localStorage (key `egurukul-demo-v1`). Clear site data to reset.
- All content (videos, QBanks, tests, plans, orders, schedules) is sample data defined in `assets/js/app.js`. Replace it with your API when the backend is ready.
- Text in square brackets, such as `[price]` or `[Add your refund policy]`, is a placeholder to fill in.
- Payments and the AI Guru chat are demo-only.
