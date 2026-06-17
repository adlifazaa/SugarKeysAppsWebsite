# Sugar Keys Apps — Official Website

Production-ready static website for [sugarkeysapps.com](https://sugarkeysapps.com).

Built with pure HTML5, CSS3, and vanilla JavaScript — no frameworks, no build tools, no dependencies.

## Files

| File | Purpose |
|------|---------|
| `index.html` | Homepage with hero, about, apps, and contact sections |
| `privacy-policy.html` | Full privacy policy for Google Play & AdMob compliance |
| `styles.css` | All styles (mobile-first, responsive) |
| `script.js` | Navigation, scroll effects, reveal animations |
| `robots.txt` | Search engine crawler directives |
| `sitemap.xml` | XML sitemap for SEO |
| `app-ads.txt` | Google AdMob / app-ads.txt verification |

## Local Preview

Open `index.html` directly in any modern browser. No server or installation required.

## Deployment Guide

### Option 1: GitHub Pages

1. **Create a GitHub repository**
   ```bash
   git init
   git add .
   git commit -m "Initial Sugar Keys Apps website"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/sugarkeysapps.git
   git push -u origin main
   ```

2. **Enable GitHub Pages**
   - Go to your repository on GitHub
   - Click **Settings** → **Pages**
   - Under **Source**, select **Deploy from a branch**
   - Choose branch: `main`, folder: `/ (root)`
   - Click **Save**

3. **Your site will be live at:**
   `https://YOUR_USERNAME.github.io/sugarkeysapps/`

4. **Connect custom domain (sugarkeysapps.com)**
   - In **Settings** → **Pages** → **Custom domain**, enter `sugarkeysapps.com`
   - GitHub will create a `CNAME` file automatically
   - Add the DNS records listed in the [DNS Configuration](#dns-configuration-godaddy) section below

5. **Enable HTTPS**
   - After DNS propagates, check **Enforce HTTPS** in GitHub Pages settings

---

### Option 2: Cloudflare Pages

1. **Push code to GitHub** (same as steps 1 above)

2. **Connect to Cloudflare Pages**
   - Log in to [Cloudflare Dashboard](https://dash.cloudflare.com)
   - Go to **Workers & Pages** → **Create** → **Pages** → **Connect to Git**
   - Select your GitHub repository
   - Configure build settings:
     - **Framework preset:** None
     - **Build command:** (leave empty)
     - **Build output directory:** `/`
   - Click **Save and Deploy**

3. **Add custom domain**
   - In your Pages project, go to **Custom domains**
   - Click **Set up a custom domain**
   - Enter `sugarkeysapps.com` and `www.sugarkeysapps.com`

4. **Your site will be live at:**
   `https://sugarkeysapps.com`

Cloudflare automatically provisions SSL certificates and CDN caching.

---

## DNS Configuration (GoDaddy)

Use these exact DNS records in your GoDaddy DNS management for `sugarkeysapps.com`.

### If using Cloudflare Pages (Recommended)

First, change your domain nameservers in GoDaddy to Cloudflare's nameservers (provided when you add the site to Cloudflare). Then add these records in **Cloudflare DNS**:

| Type | Name | Content | Proxy | TTL |
|------|------|---------|-------|-----|
| `CNAME` | `@` | `YOUR_PROJECT.pages.dev` | Proxied (orange cloud) | Auto |
| `CNAME` | `www` | `YOUR_PROJECT.pages.dev` | Proxied (orange cloud) | Auto |

> Replace `YOUR_PROJECT.pages.dev` with your actual Cloudflare Pages subdomain (e.g., `sugarkeysapps.pages.dev`).

### If using GitHub Pages

Add these records in **GoDaddy DNS Management**:

| Type | Name | Value | TTL |
|------|------|-------|-----|
| `A` | `@` | `185.199.108.153` | 600 |
| `A` | `@` | `185.199.109.153` | 600 |
| `A` | `@` | `185.199.110.153` | 600 |
| `A` | `@` | `185.199.111.153` | 600 |
| `CNAME` | `www` | `YOUR_USERNAME.github.io` | 600 |

> Replace `YOUR_USERNAME` with your GitHub username.

### Verify app-ads.txt

After deployment, confirm the file is accessible at:

```
https://sugarkeysapps.com/app-ads.txt
```

Expected content (single line):

```
google.com, pub-2257421593045125, DIRECT, f08c47fec0942fa0
```

### Verify sitemap

```
https://sugarkeysapps.com/sitemap.xml
```

### Verify privacy policy

```
https://sugarkeysapps.com/privacy-policy.html
```

---

## Google Play & AdMob Checklist

- [ ] Website live at `https://sugarkeysapps.com`
- [ ] Privacy policy accessible at `https://sugarkeysapps.com/privacy-policy.html`
- [ ] `app-ads.txt` accessible at `https://sugarkeysapps.com/app-ads.txt`
- [ ] Developer website URL set in Google Play Console
- [ ] AdMob app-ads.txt verification passes
- [ ] HTTPS enabled on all pages

---

## Contact

**Email:** sugarkeysapps@gmail.com

© 2026 Sugar Keys Apps. All rights reserved.
