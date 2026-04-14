# Smash Keys

A tiny **keyboard and touch playground** for toddlers: press keys on a computer or tap the screen on a phone or tablet. Visual bursts, sounds, optional themes, and a simple PWA shell.

## Run locally

This repo is static files only. Serve the root folder over HTTP (required for the service worker and some APIs):

```bash
npx serve .
# or: python3 -m http.server 8080
```

Open the URL shown (e.g. `http://localhost:3000`).

## Deploy

Host the project root on any static host (e.g. GitHub Pages, Vercel, Netlify). Point the site root at the folder that contains `index.html` and `sw.js`.

**Link previews (Open Graph):** `index.html` includes `og:*` and Twitter Card tags pointing at `og-image.jpg`, with `canonical` / `og:url` / `og:image` set to the **deployed origin** (currently `https://smash-keys.vercel.app/`). If you change host or add a custom domain, update those same absolute URLs so shared links resolve the image.

## iOS / Safari

- **Sound:** Safari may keep the Web Audio context **suspended** until there is a **user gesture**. The app resumes audio on Start and also tries once on the first pointer/touch after play begins. If you still hear nothing, tap the screen or press a key once.
- **Add to Home Screen:** Use Share → Add to Home Screen for a full-screen style experience.

## PWA / offline

- A **service worker** caches core assets. After a deploy, the cache version in `sw.js` is bumped so old caches can be cleared on activate.
- **Network-first** navigation keeps HTML fresh; icons and the manifest use cache-first where configured.

## Settings (Options on the home screen)

- **Theme** — Visual palette, emoji sets, and themed sounds (Shapes keeps the original sound mapping).
- **Play mode** — **Classic** is the original sandbox. **Groove** adds a soft drum loop while you play, with tempo (BPM) and beat strength in Options. **Jam** maps keys and touch-melody areas to a pentatonic scale so improvised lines tend to blend nicely (still no rules or scoring).
- **Letter learning** — Speaks letters and numbers when keys are pressed (keyboard only); uses the browser’s text-to-speech (quality varies by OS).
- **Volume / Mute** — Master gain for all synthesized sounds; saved in the browser.
- **Bouncy letters & shapes (calmer motion)** — Enables collision physics and **reduces** particles, trails, and surprise bursts so the screen stays a bit calmer.

While playing, a small **session counter** shows **keys** on desktop and **touches** on mobile (not saved after Quit).

## License

Use and modify freely for personal projects.
