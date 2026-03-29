# GitHub Pages Deployment Guide

## Quick Deploy (Auto-Company)

```bash
cd ~/auto-company/projects/affiliate-content-engine

# Initialize git if not done
git init
git add .
git commit -m "Update affiliate content engine"

# Add remote (create repo on GitHub first)
git remote add origin https://github.com/USER/affiliate-content-engine.git
git push -u origin main
```

Then enable GitHub Pages in repo Settings → Pages → Source: main branch

## Deployment Options

### Option 1: GitHub Pages (Recommended)
1. Create new GitHub repo: https://github.com/new
2. Push code: `git push -u origin main`
3. Enable Pages: Settings → Pages → Source: main branch
4. Wait 2-3 minutes, site live at: `https://USER.github.io/repo-name`

### Option 2: Netlify (Free)
1. Go to https://netlify.com
2. Drag and drop the `affiliate-content-engine` folder
3. Instant deployment, free SSL

### Option 3: Vercel (Free)
1. Go to https://vercel.com
2. Import from GitHub or drag folder
3. Instant deployment, free SSL

## Manual Upload (Cloudflare)

If you have Cloudflare access:
1. Go to: https://dash.cloudflare.com
2. Workers & Pages → affiliate-content-engine-92g
3. Deploy → Upload directory
4. Select all files from this folder

## Verification

After deployment, verify:
1. Sitemap accessible: `https://your-domain/sitemap.xml`
2. RSS feed accessible: `https://your-domain/feed.xml`
3. Test one article: `https://your-domain/blog/helium-10-review-2026.html`
