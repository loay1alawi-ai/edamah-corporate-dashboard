# Edamah Corporate Performance Dashboard — deploy to Vercel

This folder is a self-contained static site (`index.html`, no build step, no dependencies). Vercel will serve it as-is.

## Option A — Vercel CLI (fastest)

From this folder:

```bash
npx vercel login      # opens a browser to authenticate your Vercel account
npx vercel            # deploys a preview URL
npx vercel --prod     # promotes to your production URL (the one to share)
```

The first `vercel` run will ask a few setup questions (project name, link to existing project, etc.) — defaults are fine for a single static page.

## Option B — No CLI, drag and drop

1. Go to https://vercel.com/new
2. Choose "Deploy without Git" / drag-and-drop the `dashboard` folder onto the page.
3. Vercel detects it as a static site automatically and gives you a live URL.

## Option C — Git-connected (auto-redeploy on push)

```bash
git init
git add index.html vercel.json README.md
git commit -m "Initial dashboard"
```

Push to a GitHub repo, then import that repo at https://vercel.com/new — every push to the branch will redeploy automatically.

## Notes

- Everything (CSS, JS, the logo, all KPI data) is inline in `index.html` — there's nothing else to configure or host separately.
- `vercel.json` just enables clean URLs; it's optional for a single-page site.
- Local sanity check before deploying: `python3 -m http.server 8080` from this folder, then open http://localhost:8080.
