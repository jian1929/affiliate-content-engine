# Deployment Guide — Affiliate Content Engine

## Current Version: v6 (Cycle #273)

**Location:** `~/auto-company/projects/affiliate-content-engine/`
**Zip Package:** `~/auto-company/projects/affiliate-content-engine/affiliate-content-engine-v6.zip`

---

## Option 1: Cloudflare Pages (Recommended)

### Prerequisites
1. Log in to Cloudflare: https://dash.cloudflare.com
2. Navigate to Workers & Pages → Create Application
3. Select "Pages" → "Upload assets"

### Steps
1. Download the zip file from: `~/auto-company/affiliate-content-engine-v261.zip`
2. Unzip the file
3. Upload the entire `affiliate-content-engine` folder
4. Set build settings: None (static site)
5. Deploy

**Note:** Each deployment creates a new URL. Use Cloudflare's custom domains to maintain the same URL.

---

## Option 2: GitHub Pages (Free)

### Prerequisites
1. Create GitHub repository: https://github.com/new
2. Initialize git in the project folder

### Steps
```bash
cd ~/auto-company/projects/affiliate-content-engine

# Initialize git (if not already)
git init
git add .
git commit -m "v261 - 29 SEO articles, updated sitemap"

# Add remote (replace with your repo)
git remote add origin https://github.com/YOUR_USERNAME/affiliate-content-engine.git
git push -u origin main

# Enable GitHub Pages in repository settings
# Settings → Pages → Source: main branch
```

---

## Option 3: Netlify (Free + Drag & Drop)

### Steps
1. Go to: https://app.netlify.com/drop
2. Drag and drop the `affiliate-content-engine` folder
3. Done! Get instant URL

---

## Option 4: Vercel (Free)

### Steps
```bash
# Install Vercel CLI
npm i -g vercel

# Deploy
cd ~/auto-company/projects/affiliate-content-engine
vercel
```

---

## Post-Deployment Checklist

After deployment, complete these steps:

### 1. Submit to Google Search Console
1. Go to: https://search.google.com/search-console
2. Add your new URL as a property
3. Submit sitemap: `https://YOUR-DOMAIN/sitemap.xml`

### 2. Update Affiliate Links
Search for `autocomsuite-20` in all HTML files and replace with your actual affiliate tags:

| Program | Affiliate Tag Format | Replace With |
|---------|-------------------|-------------|
| Helium 10 | `?ref=YOURNAME` | `?ref=yourname` |
| Jungle Scout | `?aid=YOURNAME` | `?aid=yourname` |
| Keepa | Custom link | Your actual link |

### 3. Join Affiliate Programs
- **Helium 10**: https://www.helium10.com/affiliates
- **Jungle Scout**: https://www.junglescout.com/affiliate
- **Keepa**: https://keepa.com/#!AffiliateProgram

### 4. Track Performance
- Set up Google Analytics (GA4)
- Monitor Search Console for impressions/clicks
- Check affiliate dashboard for earnings

---

## URL Structure

```
/
├── index.html              # Homepage
├── robots.txt             # SEO robots file
├── sitemap.xml            # XML sitemap
├── amazon-seller-playbook.html
├── blog/
│   ├── how-to-sell-on-amazon-2026.html (NEW)
│   ├── amazon-fba-fees-2026.html (NEW)
│   ├── best-amazon-product-research-tools.html (NEW)
│   ├── amazon-repricing-strategy-2026.html (NEW)
│   ├── amazon-seller-dashboard-guide.html (NEW)
│   ├── best-amazon-repricing-tools-2026.html
│   ├── best-amazon-seller-tools-2026.html
│   ├── amazon-competitor-intelligence-guide.html
│   ├── amazon-seller-automation-guide.html
│   ├── amazon-price-tracking-tools-2026.html
│   ├── fba-sellers-complete-guide.html
│   ├── jungle-scout-alternatives-2026.html
│   ├── helium-10-review-2026.html
│   ├── helium-10-vs-jungle-scout.html
│   ├── keepa-vs-camelcamelcamel.html
│   ├── buy-box-strategy-amazon.html
│   ├── amazon-ppc-guide-2026.html
│   ├── amazon-fba-calculator.html
│   ├── amazon-seller-success-stories.html
│   ├── twitter-thread-generator.html
│   ├── reddit-post-generator.html
│   ├── linkedin-post-generator.html
│   ├── share-scheduler.html
│   ├── tiktok-shorts-generator.html
│   ├── pinterest-pin-generator.html
│   ├── guest-post-outreach.html
│   └── link-in-bio.html
```

---

## Quick Deploy Commands

### Cloudflare (if authenticated)
```bash
cd ~/auto-company/projects/affiliate-content-engine
npx wrangler pages deploy .
```

### GitHub
```bash
cd ~/auto-company/projects/affiliate-content-engine
git add .
git commit -m "v261 - 29 SEO articles"
git push
```

### Netlify
Drag folder to https://app.netlify.com/drop

---

## Files Modified This Cycle (v6 — Cycle #273)

### New Files Created
1. `syndication-executor.html` — One-click syndication dashboard
2. `syndicate-devto-browser.js` — Playwright automation for Dev.to
3. `ping-search-engines.sh` — Script to ping Google/Bing
4. `DEVTO_CONTENT_PACK.md` — Dev.to syndication guide
5. `HASHNODE_CONTENT_PACK.md` — Hashnode syndication guide
6. `MEDIUM_CONTENT_PACK.md` — Medium syndication guide
7. `syndicate-all.sh` — Master syndication script

### Files Updated
1. `index.html` — Added Syndication Executor link
2. `sitemap.xml` — Added syndication-executor.html

### Total Content (v6)
- **44 SEO articles** targeting Amazon seller keywords
- **4 syndication platforms** (Dev.to, Hashnode, Medium, Substack)
- **144 pre-generated social posts**
- **Traffic tools** (batch generator, submission tracker, indexing)
