# Deployment Guide

## 1. Create GitHub Repository

1. Go to https://github.com/new
2. Name: `LandyGauge` (or `landygauge-site`)
3. Set to **Public** (required for free GitHub Pages)
4. Do NOT initialise with README (we already have content)

## 2. Push the Site

```bash
cd /Users/pbarnard/Documents/Web/LandyGauge
git remote add origin https://github.com/paulrbarnard/LandyGauge.git
git push -u origin main
```

## 3. Enable GitHub Pages

1. Go to your repo → **Settings** → **Pages**
2. Under "Build and deployment", set Source to **GitHub Actions**
3. The workflow will run automatically on the next push

## 4. Configure Custom Domain on GitHub

1. In the same Pages settings page, enter `www.toxiccelery.co.uk` in the Custom domain field
2. Click Save
3. Wait for the DNS check (it will fail until you do step 5)

## 5. Configure DNS at 123-Reg

Log into https://www.123-reg.co.uk and go to your domain `toxiccelery.co.uk` DNS settings.

### For `www.toxiccelery.co.uk` (recommended primary):

Add a **CNAME** record:
- **Host**: `www`
- **Points to**: `paulrbarnard.github.io`
- **TTL**: 3600

### For bare `toxiccelery.co.uk` (redirect to www):

Add these **A** records pointing to GitHub's IP addresses:
- **Host**: (leave blank or `@`)
- **Points to**: `185.199.108.153`
- **Points to**: `185.199.109.153`
- **Points to**: `185.199.110.153`
- **Points to**: `185.199.111.153`

### Delete old records

Remove any existing A records or CNAME records for `www` or `@` that point to HostPapa.

## 6. Verify and Enable HTTPS

1. Wait 10-30 minutes for DNS to propagate
2. Go back to GitHub repo → Settings → Pages
3. The DNS check should now pass
4. Tick **Enforce HTTPS**

## 7. Create CNAME file

This is already handled by GitHub when you set the custom domain in Settings, but if needed:

```bash
echo "www.toxiccelery.co.uk" > static/CNAME
git add static/CNAME && git commit -m "Add CNAME for custom domain" && git push
```

## Local Development

To preview the site locally:

```bash
cd /Users/pbarnard/Documents/Web/LandyGauge
~/bin/hugo server --buildDrafts
```

Then open http://localhost:1313/

## Adding Content

All content is Markdown files in the `content/` directory. To add a new blog post:

```bash
~/bin/hugo new content blog/my-new-post.md
```

Edit the file, set `draft: false` when ready, commit and push. The site rebuilds automatically.
