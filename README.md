# Scoutline

Mobile-first football scouting app for English academies, League One, League Two and non-league talent. Includes verified scouting leads, player watchlists, personal match reports, comparisons and optional private team collaboration.

## Deployment

This repository is ready for **Cloudflare Workers Builds**. It is intended to update the existing Cloudflare Worker **`delicate-bird-c3d7`**, rather than create a new website.

In Cloudflare:

1. Go to **Workers & Pages → delicate-bird-c3d7 → Settings → Builds → Connect**.
2. Choose **GitHub → jmeasom81-cmd/Scoutline**, production branch **`main`**.
3. Leave **Root directory** blank (repository root).
4. Leave **Build command** blank (static site; no compilation needed).
5. Use **Deploy command:** `npx wrangler deploy`.
6. Save/connect. Check the build logs and test the existing Worker URL.
7. Future updates pushed to `main` will then deploy automatically.

The `wrangler.jsonc` Worker name **must match** the existing Cloudflare Worker. Static site files live in `public/`.

## Data and privacy

The public repository contains static application code and curated scouting leads, **not users' passwords or private scouting records**. Personal records are kept in the browser unless explicitly published to a private scouting team. Shared records live in a separate Neon project with authentication and row-level database access controls.

Do not commit database passwords, API secret keys, private scouting exports or account credentials.

## App files

- `public/index.html`: complete V6 single-page application.
- `public/sw.js`: offline/cache support.
- `public/manifest.webmanifest`, `public/icon.svg`: installable web app.
- `public/_headers`, `public/robots.txt`: security and indexing controls.
- `wrangler.jsonc`: existing-Worker deployment configuration.

## Automatic deployment smoke test

A documentation-only commit on 17 October 2026 verifies whether Cloudflare Workers Builds is listening for pushes to the `main` branch. This change does not alter scouting data or application behaviour.
