# Oversight Signal Test

A policy-diagnostic tool. Paste a draft "human oversight" definition and see whether it would
actually reach a human across four fictional AI-incident scenarios, scored against 7 heuristic
criteria (named role, review timing, threshold, reviewer authority, sector-agnostic scope,
noise/materiality handling, audit trail).

**This is an automated keyword scan — a first-pass signal, not a definitive legal or policy audit.**

## Structure

- `index.html` — landing page
- `tool.html` — the diagnostic tool
- `assets/hero-signal.json` — hand-authored Lottie animation for the hero background (see note below)
- `assets/vendor/lottie-light.min.js` — self-hosted `lottie-web` (SVG renderer build), no CDN dependency

No build step. Static HTML/CSS/JS throughout.

## Local preview

Open `index.html` directly in a browser, or serve the folder:

```
npx serve .
```

## Deploying to Vercel

This is a zero-config static site — Vercel needs no build command or output directory.

1. Go to [vercel.com/new](https://vercel.com/new) and import this GitHub repository.
2. Framework preset: **Other** (or leave auto-detected — there's nothing to build).
3. Deploy. `index.html` serves at the root; the tool is linked from there and also reachable
   directly at `/tool.html` (or `/tool`, since `vercel.json` sets `cleanUrls: true`).

Every future push to the connected branch will auto-deploy.

## Hero animation note

The hero's gradient-blob pulse is a real `lottie-web` integration (npm-installed, self-hosted —
no CDN), but the LottieFiles.com site itself was unreachable from the sandbox this was built in
(network policy blocked it), so the animation JSON is hand-authored rather than sourced from
LottieFiles as originally intended. It's fully swappable: replace `assets/hero-signal.json` with
any exported Lottie JSON and the loader in `index.html` picks it up as-is.
