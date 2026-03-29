# GitHub Pages Deployment Guide

This guide explains how to deploy the Affiliate Content Engine to GitHub Pages as an alternative to Cloudflare Pages.

## Why GitHub Pages?

- **Free hosting** — No Cloudflare account needed
- **Custom domain support** — Use your own domain
- **Simple deployment** — Just push to GitHub
- **Reliable CDN** — Fast loading worldwide

## Option 1: Quick Deploy (5 minutes)

### Step 1: Create a New GitHub Repository

1. Go to [github.com/new](https://github.com/new)
2. Name it: `affiliate-content-engine`
3. Make it Public
4. Click "Create repository"

### Step 2: Push Your Files

```bash
cd ~/auto-company/projects/affiliate-content-engine

# Initialize git if not already
git init
git add .
git commit -m "Initial commit - Affiliate Content Engine"

# Add your GitHub repo (replace with your username)
git remote add origin https://github.com/YOUR_USERNAME/affiliate-content-engine.git
git branch -M main
git push -u origin main
```

### Step 3: Enable GitHub Pages

1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll to "Pages" section (left sidebar)
4. Under "Source", select "Deploy from a branch"
5. Select "main" branch and "/ (root)" folder
6. Click "Save"

### Step 4: Wait for Deployment

GitHub Pages will deploy your site. After 1-2 minutes, your site will be live at:

```
https://YOUR_USERNAME.github.io/affiliate-content-engine/
```

## Option 2: Custom Domain

### Setting Up Custom Domain

1. In your GitHub repository Settings → Pages
2. Enter your custom domain (e.g., `affiliate.yourdomain.com`)
3. Add the following DNS records at your domain provider:

```
Type: CNAME
Name: affiliate
Value: YOUR_USERNAME.github.io
TTL: 3600
```

4. Wait for DNS propagation (up to 24 hours, usually 5-30 minutes)
5. Enable "Enforce HTTPS" after DNS is verified

## Option 3: Deploy with GitHub Actions (Auto-Deploy)

Create `.github/workflows/deploy.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v4
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: '.'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

This automatically deploys every push to main.

## Updating Your Site

### Method 1: Push Updates

```bash
# Make changes to files
git add .
git commit -m "Update content"
git push
```

GitHub Pages will automatically rebuild and deploy.

### Method 2: Upload Files Directly

1. Go to your repository on GitHub
2. Click "Add file" → "Create new file" or "Upload files"
3. Add or edit your content
4. Commit changes

## File Structure for GitHub Pages

```
affiliate-content-engine/
├── index.html
├── blog/
│   ├── article-1.html
│   ├── article-2.html
│   └── ...
├── tools/
│   ├── tool-1.html
│   └── ...
├── sitemap.xml
├── README.md
└── .github/
    └── workflows/
        └── deploy.yml
```

## Troubleshooting

### 404 Errors

If pages show 404:
1. Check that your file names match exactly (case-sensitive)
2. Ensure `index.html` exists in the root
3. Wait 2 minutes for initial deployment

### Jekyll Processing

If your site isn't deploying:
1. Add an empty `.nojekyll` file to the root
2. Or add to `_config.yml`: `future: true`

### Build Errors

Check the Actions tab in your repository for error logs.

## Quick Reference

| Task | Command |
|------|---------|
| Clone repo | `git clone https://github.com/YOUR_USERNAME/affiliate-content-engine.git` |
| Pull latest | `git pull origin main` |
| Check status | `git status` |
| Add changes | `git add .` |
| Commit | `git commit -m "Your message"` |
| Push | `git push origin main` |

## Support

- GitHub Pages Docs: https://docs.github.com/en/pages
- Custom Domains: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site

---

**Your Site URL:** `https://YOUR_USERNAME.github.io/affiliate-content-engine/`
