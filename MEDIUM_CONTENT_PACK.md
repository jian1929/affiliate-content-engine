# Medium Content Package — Cycle #273

## Setup Instructions

1. Go to https://medium.com/me/settings/security
2. Generate an integration token
3. Export it: `export MEDIUM_TOKEN='your_token'`
4. Use the API to create posts

---

## API Details

**Endpoint:** `POST https://api.medium.com/v1/users/{userId}/posts`

**Headers:**
```
Authorization: Bearer {token}
Content-Type: application/json
```

---

## Article 1: Amazon PPC Guide

**Title:** The Complete Amazon PPC Guide for 2026

**Tags:** amazon-ppc, ecommerce, fba, advertising, amazon-seller

**Canonical URL:** https://ae16e0d4.affiliate-content-engine-92g.pages.dev/blog/amazon-ppc-guide-2026.html

**Tags for Medium:** amazon, ppc, advertising, ecommerce, business

---

## Article 2: Buy Box Strategy

**Title:** How to Win the Amazon Buy Box in 2026

**Tags:** buybox, amazon, ecommerce, repricing, fba

**Canonical URL:** https://ae16e0d4.affiliate-content-engine-92g.pages.dev/blog/amazon-repricing-strategy-2026.html

**Tags for Medium:** amazon, buybox, ecommerce, business, selling

---

## Article 3: Competitor Intelligence

**Title:** Amazon Competitor Intelligence: The Complete Guide

**Tags:** competitor-intelligence, amazon, ecommerce, fba

**Canonical URL:** https://ae16e0d4.affiliate-content-engine-92g.pages.dev/blog/amazon-competitor-intelligence-guide.html

**Tags for Medium:** amazon, ecommerce, business, strategy

---

## cURL Example

```bash
# Get user ID first
curl -H "Authorization: Bearer $MEDIUM_TOKEN" \
     https://api.medium.com/v1/me

# Create post
curl -X POST "https://api.medium.com/v1/users/{userId}/posts" \
  -H "Authorization: Bearer $MEDIUM_TOKEN" \
  -H "Content-Type: application/json" \
  -H "Accept: application/json" \
  -d '{
    "title": "Your Article Title",
    "contentFormat": "markdown",
    "content": "Your Markdown content...",
    "tags": ["amazon", "ecommerce", "fba"],
    "canonicalUrl": "https://your-site.com/article.html",
    "publishStatus": "public"
  }'
```

---

## Manual Posting Instructions

1. Copy article content
2. Go to https://medium.com/new/story
3. Select "Import a story"
4. Paste URL of original article
5. Medium will auto-format
6. Add tags
7. Publish with canonical link back to original

---
