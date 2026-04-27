# FairRent NYC

> Instantly check if your NYC apartment is fairly priced before signing your lease.

**Live demo:** https://fairrentnyc.com  
**Stack:** Pure HTML/CSS/JS — zero dependencies, zero build step  
**Hosting:** Vercel (static)

---

## File Structure

```
fairrent-nyc/
├── index.html      # Full app — all HTML, CSS, JS in one file
├── vercel.json     # Vercel config: security headers, caching, routing
├── robots.txt      # Search engine crawl rules
├── sitemap.xml     # SEO sitemap (update URL if you use a custom domain)
└── README.md       # This file
```

---

## Run Locally

No build tools or npm required. Just open the file:

**Mac/Linux:**
```bash
open index.html
# or
npx serve .        # serves at http://localhost:3000
```

**Windows:**
```
Double-click index.html
```

**Optional — local dev server with live reload:**
```bash
npx browser-sync start --server --files "*.html"
```

---

## Deploy to Vercel

### Option A — Vercel CLI (recommended)

```bash
# 1. Install Vercel CLI (one-time)
npm install -g vercel

# 2. Inside the project folder
cd fairrent-nyc

# 3. Deploy
vercel

# Follow the prompts:
#   Set up and deploy? → Y
#   Which scope?       → your account
#   Link to existing?  → N
#   Project name?      → fairrent-nyc  (or anything)
#   Directory?         → ./  (just press Enter)
#
# You'll get a preview URL instantly.

# 4. Promote to production
vercel --prod
```

### Option B — Vercel Dashboard (no CLI)

1. Push this folder to a **GitHub** repo (public or private)
2. Go to [vercel.com/new](https://vercel.com/new)
3. Import the GitHub repo
4. Framework Preset → **Other**
5. Root Directory → `./` (leave as-is)
6. Build Command → *(leave empty)*
7. Output Directory → `./` (leave as-is)
8. Click **Deploy**

---

## Add a Custom Domain

1. In the Vercel dashboard → your project → **Settings → Domains**
2. Add your domain (e.g. `fairrentnyc.com`)
3. Update your DNS registrar with the records Vercel shows you
4. Update these two lines in `sitemap.xml` and `index.html` (the `<link rel="canonical">` and og:url tags) to match your domain

---

## Update the Data

All benchmark rent data lives in `index.html` inside the `DATA` array (search for `const DATA = [`). Each entry looks like:

```js
{ area: "Williamsburg", beds: "1 Bedroom", avg: 4400 }
```

Edit `avg` values or add new neighborhoods — no rebuild needed. Just redeploy.

---

## Customisation Checklist

- [ ] Replace `https://fairrentnyc.com` with your actual domain in `index.html`, `robots.txt`, `sitemap.xml`
- [ ] Create an `og-image.png` (1200×630px) and add it to the root folder for social sharing previews
- [ ] Add Google Analytics or Plausible by inserting a `<script>` tag just before `</head>` in `index.html`
- [ ] Update `sitemap.xml` `<lastmod>` date when you make significant changes

---

## License

MIT — use freely, no attribution required.
