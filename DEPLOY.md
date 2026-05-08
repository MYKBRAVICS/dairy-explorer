# 🐄 Dairy Explorer — Deployment Guide

A self-contained Progressive Web App (PWA) — works online, offline, and can be installed on any device.

---

## 📁 File Structure

```
dairy-explorer/
├── index.html        ← Main app (all CSS + content inline)
├── manifest.json     ← PWA identity & install config
├── sw.js             ← Service worker (offline caching)
└── icons/
    ├── icon-192.png  ← App icon (Android / Chrome)
    └── icon-512.png  ← App icon (splash screens)
```

> **Icons:** Replace the placeholder icons with your own branded artwork.  
> Recommended: a green rounded-square with a cow/milk motif. Use a tool like  
> [realfavicongenerator.net](https://realfavicongenerator.net) to generate all sizes.

---

## 🚀 Option 1 — GitHub Pages (Free, Recommended)

1. Create a free account at [github.com](https://github.com)
2. Click **New repository** → name it `dairy-explorer` → set to **Public**
3. Upload all four files (index.html, manifest.json, sw.js, icons/)
4. Go to **Settings → Pages → Branch: main → Save**
5. Your app is live at: `https://YOUR-USERNAME.github.io/dairy-explorer/`

**Custom domain (optional):**
- Buy a domain (e.g. `dairyexplorer.app`)
- In GitHub Pages settings, add your custom domain
- Point your domain's DNS `CNAME` record to `YOUR-USERNAME.github.io`

---

## 🌐 Option 2 — Netlify Drop (Fastest, No account needed)

1. Go to [app.netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop the entire `dairy-explorer/` folder onto the page
3. Netlify gives you a live URL instantly (e.g. `https://random-name.netlify.app`)
4. Optionally sign up to claim a custom subdomain or connect your own domain

---

## ☁️ Option 3 — Cloudflare Pages (Best performance globally)

1. Sign up at [pages.cloudflare.com](https://pages.cloudflare.com)
2. Connect your GitHub repo **or** use Direct Upload
3. Build settings: leave blank (static site, no build step)
4. Deploy — Cloudflare's global CDN serves the app with very fast load times
5. Custom domains are free and include automatic HTTPS

---

## 📱 Installing as a Mobile App (PWA)

### Android (Chrome)
1. Open the site URL in Chrome
2. Tap the **⋮** menu → **Add to Home Screen**
3. The app installs with its own icon and runs fullscreen

### iPhone / iPad (Safari)
1. Open the site URL in Safari
2. Tap the **Share** button (box with arrow) → **Add to Home Screen**
3. The app installs and launches fullscreen

### Desktop (Chrome / Edge)
1. Visit the site URL
2. Click the **install icon** (⊕) in the address bar → **Install**
3. The app opens as a standalone window

---

## 🔒 HTTPS Requirement

**The service worker and PWA install only work over HTTPS.**  
All three hosting options above provide HTTPS automatically for free.

> For local testing, run: `npx serve .` (requires Node.js) — this serves on `localhost` which also allows service workers.

---

## ✏️ Updating Content

All content is in `index.html`. To update:
1. Edit `index.html` in any text editor
2. Re-upload / push to your hosting provider
3. Increment the cache name in `sw.js` from `dairy-explorer-v1` to `dairy-explorer-v2` so returning users get the fresh content

---

## ⚡ Performance Tips

- The app is ~180 KB of HTML/CSS/JS — loads in under 1 second on 3G
- After the first visit, all content is cached offline by the service worker
- Fonts are loaded from Google Fonts; they degrade gracefully if offline

---

*© 2026 Dairy Explorer · Expert Reference Guide · For Professional & Educational Use*
