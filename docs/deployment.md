# Deployment Guide

## Table of Contents

1. [Deployment Overview](#deployment-overview)
2. [Netlify Deployment](#netlify-deployment-recommended)
3. [Vercel Deployment](#vercel-deployment-alternative)
4. [GitHub Pages](#github-pages-alternative)
5. [AWS Deployment](#aws-deployment)
6. [SSL Certificates](#ssl-certificates)
7. [CDN Integration](#cdn-integration)
8. [Performance Optimization](#performance-optimization)
9. [Monitoring & Maintenance](#monitoring--maintenance)

---

## Deployment Overview

### Deployment Platforms

| Platform | Ease | Performance | Cost | SSL | CDN |
|----------|------|-------------|------|-----|-----|
| **Netlify** | 🟢 Very Easy | 🟢 Excellent | 🟢 Free | ✅ Auto | ✅ Global |
| **Vercel** | 🟢 Very Easy | 🟢 Excellent | 🟢 Free | ✅ Auto | ✅ Global |
| **GitHub Pages** | 🟡 Easy | 🟡 Good | 🟢 Free | ✅ Auto | ⚠️ Limited |
| **AWS S3+CloudFront** | 🔴 Complex | 🟢 Excellent | 🟡 Paid | ✅ Manual | ✅ Global |

### Recommended: Netlify

**Why Netlify?**
- ✅ Zero configuration needed
- ✅ Automatic HTTPS/SSL
- ✅ Global CDN
- ✅ Great free tier
- ✅ Continuous deployment
- ✅ Great dashboard

---

## Netlify Deployment (Recommended)

### Step 1: Prepare Repository

```bash
# Ensure all changes committed
git status

# Push to GitHub
git push origin main
```

### Step 2: Sign Up for Netlify

1. Go to [netlify.com](https://www.netlify.com)
2. Click "Sign up"
3. Choose "GitHub" option
4. Authorize Netlify to access GitHub

### Step 3: Create New Site

1. Click "New site from Git"
2. Select "GitHub" provider
3. Search for repository: `drshanali`
4. Click to connect

### Step 4: Configure Build Settings

**Build Settings:**
- Build command: (Leave empty - static site)
- Publish directory: `.` (dot - entire folder)

**Environment Variables:** (Optional)
- Leave empty for static site

### Step 5: Deploy

1. Click "Deploy site"
2. Wait for build (usually < 1 minute)
3. Get assigned domain: `xxxxx.netlify.app`

### Step 6: Custom Domain (Optional)

1. Go to Domain settings
2. Click "Add custom domain"
3. Enter: `drshanali.com`
4. Update DNS settings at domain registrar
5. Wait 24 hours for propagation

### Continuous Deployment

After initial setup:

```bash
# Just push to main branch
git push origin main

# Netlify automatically:
# 1. Detects changes
# 2. Builds site
# 3. Deploys changes
# 4. Updates live site
```

### Netlify Status

- Visit [app.netlify.com](https://app.netlify.com)
- Check deployment status
- View build logs
- Monitor site performance

---

## Vercel Deployment (Alternative)

### Quick Setup

1. Go to [vercel.com](https://vercel.com)
2. Click "New Project"
3. Import GitHub repository
4. Click "Deploy"
5. Done! Site is live

### Custom Domain

1. Go to Settings → Domains
2. Add custom domain
3. Update DNS records
4. Wait for verification

### Automatic Deployments

```bash
# Push to main
git push origin main

# Vercel automatically deploys
# Site updates within seconds
```

---

## GitHub Pages

### Enable GitHub Pages

1. Go to Repository Settings
2. Scroll to "GitHub Pages"
3. Select "main" branch
4. Click "Save"

### Access Your Site

- URL: `https://username.github.io/drshanali/`
- Takes 5-10 minutes for initial deployment

### Custom Domain

1. Add CNAME file to root: `drshanali.com`
2. Update DNS CNAME record
3. Wait for propagation

### Limitations

- Slightly slower than Netlify/Vercel
- No build customization
- Limited free tier
- Manual deployment only

---

## AWS Deployment

### S3 + CloudFront Setup

```bash
# 1. Create S3 bucket
aws s3 mb s3://drshanali.com

# 2. Enable static website hosting
aws s3 website s3://drshanali.com \
  --index-document index.html \
  --error-document error.html

# 3. Upload files
aws s3 sync . s3://drshanali.com \
  --exclude ".git/*" \
  --exclude ".*"

# 4. Create CloudFront distribution
# (Use AWS Console for this)

# 5. Update DNS to point to CloudFront
```

### Caching Headers

```bash
# Set cache headers
aws s3 sync . s3://drshanali.com \
  --cache-control "max-age=31536000" \
  --exclude "index.html" \
  --exclude ".*"

# HTML - no cache
aws s3 cp s3://drshanali.com/index.html \
  s3://drshanali.com/index.html \
  --metadata-directive REPLACE \
  --cache-control "max-age=3600"
```

---

## SSL Certificates

### Automatic SSL (Netlify/Vercel)

- ✅ Automatic HTTPS
- ✅ Let's Encrypt certificates
- ✅ Auto-renewal
- ✅ No configuration needed

### Manual SSL (AWS)

```bash
# Request certificate (AWS Certificate Manager)
# Verify domain ownership
# Attach to CloudFront
# Enable HTTPS only
```

### SSL Best Practices

- ✅ Always use HTTPS
- ✅ Redirect HTTP → HTTPS
- ✅ Use HSTS header
- ✅ Monitor certificate expiry

---

## CDN Integration

### Cloudflare CDN

1. Sign up at [cloudflare.com](https://www.cloudflare.com)
2. Add domain: `drshanali.com`
3. Update DNS to Cloudflare
4. Enable caching rules
5. Configure security settings

### Benefits

- ✅ Global edge caching
- ✅ DDoS protection
- ✅ Faster asset delivery
- ✅ WAF (Web Application Firewall)

### Configuration

```
Cache Level: Cache Everything
Browser Cache TTL: 1 month
Page Rules: 
  - Cache HTML: 1 hour
  - Cache CSS/JS: 1 year
```

---

## Performance Optimization

### Image Optimization

```bash
# Before deployment:
# 1. Compress all images
# 2. Use appropriate format (JPG/PNG/SVG)
# 3. Set responsive sizes
# 4. Add alt text
```

### Caching Strategy

```
Static Assets (CSS, JS, Images):
- Cache-Control: public, max-age=31536000
- Immutable after content hash

HTML:
- Cache-Control: public, max-age=3600
- Allow frequent updates

JSON/API:
- Cache-Control: private, max-age=0
- No caching
```

### Headers Configuration

**Netlify** - Create `_headers` file:

```
/*
  X-Frame-Options: DENY
  X-Content-Type-Options: nosniff
  Referrer-Policy: strict-origin-when-cross-origin
  Permissions-Policy: accelerometer=(), microphone=(), geolocation=()
```

---

## Monitoring & Maintenance

### Performance Monitoring

```bash
# Check Core Web Vitals
# 1. Google Search Console
# 2. Lighthouse CI
# 3. PageSpeed Insights
```

### Uptime Monitoring

Services:
- [Uptime Robot](https://uptimerobot.com) - Free
- [StatusPage.io](https://www.statuspage.io) - Paid
- [Pingdom](https://www.pingdom.com) - Paid

Configuration:
- Monitor: drshanali.com
- Interval: Every 5 minutes
- Alert on downtime

### Error Tracking

Services:
- [Sentry](https://sentry.io) - Error monitoring
- [LogRocket](https://logrocket.com) - User monitoring
- [DataDog](https://www.datadoghq.com) - Infrastructure

### Analytics

Services:
- [Google Analytics](https://analytics.google.com) - Free
- [Plausible](https://plausible.io) - Privacy-focused
- [Hotjar](https://www.hotjar.com) - User feedback

---

## Rollback & Recovery

### Rollback Steps

```bash
# If deployment fails:
1. Check deployment status
2. Review error logs
3. Revert to previous commit:
   git revert HEAD
   git push origin main
4. Deployment auto-triggers
5. Site reverts to last working version
```

### Disaster Recovery

- ✅ GitHub backups all code
- ✅ Regular backups recommended
- ✅ Use Git tags for releases:

```bash
git tag -a v1.0.0 -m "Release 1.0.0"
git push origin v1.0.0
```

---

## Pre-Deployment Checklist

- [ ] All links tested and working
- [ ] All images display correctly
- [ ] Mobile responsive verified
- [ ] Contact form tested
- [ ] No console errors (F12)
- [ ] Lighthouse score 90+
- [ ] SEO metadata added
- [ ] All pages indexed in sitemap
- [ ] SSL certificate configured
- [ ] DNS records updated
- [ ] CDN configured (if using)
- [ ] Monitoring enabled
- [ ] Backup strategy in place

---

## Post-Deployment Verification

1. Test live website
2. Check all pages load
3. Verify mobile responsiveness
4. Test contact form
5. Check Core Web Vitals
6. Monitor for errors
7. Verify analytics tracking
8. Check search console

---

## Quick Deployment Summary

### Netlify (30 seconds)
```bash
git push origin main
# Live in < 1 minute
```

### Vercel (1 minute)
```bash
# Connect GitHub → Deploy
# Live in < 1 minute
```

### GitHub Pages (10 minutes)
```bash
# Settings → Enable GitHub Pages
# Live in 5-10 minutes
```

---

**Last Updated**: June 1, 2026  
**Status**: Production Ready
