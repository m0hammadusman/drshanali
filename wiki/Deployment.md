# Deployment Guide

Quick reference for deploying the site to production.

---

## Quick Deploy (30 seconds)

### Netlify Quick Deploy

1. Go to [netlify.com](https://netlify.com)
2. Click "New site from Git"
3. Connect GitHub account
4. Select repository
5. Click Deploy
6. Done! Site is live

---

## Detailed Setup

### Netlify (Recommended)

**Step 1: Sign Up**
- Visit [netlify.com](https://netlify.com)
- Sign up (use GitHub)
- Authorize Netlify

**Step 2: Create Site**
- Click "New site from Git"
- Choose GitHub
- Search for repository
- Select repository

**Step 3: Configure**
- Build command: (Leave empty)
- Publish directory: `.` (dot)
- Click Deploy

**Step 4: Monitor**
- View deployment status
- Check build logs
- Once completed, get assigned URL

**Step 5: Custom Domain (Optional)**
- Go to Domain settings
- Add custom domain
- Update DNS at registrar
- Wait 24 hours

---

### Vercel

**Quick Setup**
1. Go to [vercel.com](https://vercel.com)
2. Click "New Project"
3. Import GitHub repo
4. Click Deploy
5. Done!

**Custom Domain**
1. Settings → Domains
2. Add domain
3. Update DNS
4. Wait for verification

---

### GitHub Pages

**Enable**
1. Go to repository Settings
2. Scroll to GitHub Pages
3. Select main branch
4. Click Save

**URL**: https://username.github.io/portfolio/

**Custom Domain**
1. Add CNAME file to root
2. Update DNS records
3. Wait for propagation

---

## Continuous Deployment

After initial setup, deployment is automatic!

```bash
# Just push to main
git push origin main

# Netlify/Vercel automatically:
# 1. Detects changes
# 2. Builds site
# 3. Deploys
# 4. Site updates
```

---

## Before Deployment

Checklist before going live:

- [ ] All links tested
- [ ] Images display correctly
- [ ] Mobile responsive
- [ ] No console errors
- [ ] Contact form works
- [ ] Forms validated
- [ ] Performance good
- [ ] SEO tags present
- [ ] Favicons set
- [ ] Robots.txt configured

---

## Monitoring

### Check Deployment Status
- Netlify dashboard: [app.netlify.com](https://app.netlify.com)
- Vercel dashboard: [vercel.com/dashboard](https://vercel.com/dashboard)
- GitHub Pages: GitHub → Actions tab

### Performance Monitoring
- [Google PageSpeed Insights](https://pagespeed.web.dev)
- [Lighthouse CI](https://github.com/GoogleChrome/lighthouse-ci)
- [GTmetrix](https://gtmetrix.com)

### Uptime Monitoring
- [Uptime Robot](https://uptimerobot.com)
- [StatusPage.io](https://www.statuspage.io)
- [Pingdom](https://www.pingdom.com)

---

## Common Deployment Issues

### Build Fails
- Check build logs on platform
- Verify all files committed
- Check for syntax errors
- Try local build first

### Site Not Updating
- Hard refresh browser (Ctrl+Shift+R)
- Clear browser cache
- Check deployment completed
- Wait ~1 minute

### Performance Slow
- Check file sizes
- Compress images further
- Enable CDN
- Check network tab (F12)

---

## Platform Comparison

| Feature | Netlify | Vercel | GitHub Pages |
|---------|---------|--------|-------------|
| **Ease** | Very Easy | Very Easy | Easy |
| **Performance** | Excellent | Excellent | Good |
| **Cost** | Free | Free | Free |
| **SSL** | Automatic | Automatic | Automatic |
| **CDN** | Global | Global | Limited |
| **Custom Domain** | Yes | Yes | Yes |
| **Build Time** | ~1 min | ~1 min | ~5 min |
| **Support** | Excellent | Excellent | GitHub |

---

## Environment Variables

**Not needed for static sites!**

For future backend integration, use platform-specific methods:
- **Netlify**: Site settings → Build & deploy → Environment
- **Vercel**: Project settings → Environment variables
- **GitHub Pages**: GitHub Secrets (if using Actions)

---

## SSL/HTTPS

All platforms provide automatic HTTPS:
- ✅ Let's Encrypt certificates
- ✅ Auto-renewal
- ✅ No configuration needed
- ✅ All traffic encrypted

---

## CDN Integration

Optionally add Cloudflare for extra speed:

1. Sign up at [cloudflare.com](https://cloudflare.com)
2. Add domain
3. Update DNS to Cloudflare
4. Configure caching rules
5. Enable security features

---

## Rollback Procedure

If something goes wrong:

```bash
# Find previous good commit
git log --oneline

# Revert to previous commit
git revert <commit-hash>

# Push changes
git push origin main

# Site auto-updates
```

---

## Post-Deployment

1. **Test Live Site**
   - Check all pages load
   - Test links
   - Check mobile view

2. **Verify Performance**
   - Run Lighthouse
   - Check load time
   - Monitor metrics

3. **Monitor Site**
   - Set up uptime monitoring
   - Enable error tracking
   - Review analytics

4. **Document**
   - Note deployment date
   - Update CHANGELOG
   - Record any issues

---

## Related Documentation

- [Installation](Installation.md) - Setup guide
- [Architecture](Architecture.md) - Technical design
- [Troubleshooting](Troubleshooting.md) - Problem solutions

---

**Last Updated**: June 1, 2026
