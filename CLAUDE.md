# CLAUDE.md — GetNetStats

Guidance for Claude Code working in this repo. Keep this file current; if it
conflicts with the code, trust the code and fix this file.

## What this is
A privacy-first network / internet-stats tool + content site on
**getnetstats.com**. Reader-supported via display ads + affiliate links. It's
the original Next.js tool-site build; the portfolio's reference standard for
structure and handoff practice is now **CleanGlowScalp**.

## Stack
- **Next.js 15.5.4** (App Router) + **React 19**, **TypeScript**.
- Static export -> `out/` (GitHub Pages serves the static output).
- `@next/third-parties` for GA4.
- Hosting: **GitHub Pages + GoDaddy DNS**.

## Where the code lives
- Build root: `./` (this folder) — run `claude` and all npm commands here.
- Deploy steps: `DEPLOY.md` — follow it exactly.
- Handoffs: `Handoffs/` — start with `GetNetStats-RESUME-HERE.md`.

## Commands
```bash
npm install
npm run dev     # local dev server
npm run build   # production build -> static export in out/
npm run lint    # next lint
```

## Layout
```
app/         routes (App Router) + layout/head (GA tag lives here)
components/   shared UI
lib/          helpers
public/       static assets (CNAME, .nojekyll, favicons)
out/          build output — the folder that gets deployed
marketing/    marketing assets + YouTube kit
```

## Conventions
- Keep the GA4 tag in the App Router head/layout; don't scatter analytics code.
- Don't hardcode the domain in components — keep canonical/site config central.
- Affiliate links: rel="nofollow sponsored noopener", target="_blank".

## Deploy
- **GitHub Pages + GoDaddy DNS.** Follow `DEPLOY.md` for the exact steps.
- `public/CNAME` (getnetstats.com) and `.nojekyll` must survive every build —
  confirm they land in `out/` before deploying.
- After deploy, check GA4 Realtime for hits.

## Working style here
- Match surrounding code; keep edits localized.
- **Confirm before anything outward-facing or irreversible:** deploys, `git push`,
  DNS, spending money, deleting content.
- Write a handoff note at the end of a real milestone.
