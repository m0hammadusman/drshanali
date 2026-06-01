# Frequently Asked Questions

## Table of Contents

1. [Getting Started](#getting-started)
2. [Deployment](#deployment)
3. [Content & Pages](#content--pages)
4. [Technical](#technical)
5. [Performance](#performance)
6. [Security & Privacy](#security--privacy)
7. [Contributing](#contributing)
8. [Troubleshooting](#troubleshooting)

---

## Getting Started

### Q: How do I set up the project locally?

A: Follow these steps:
1. Clone the repository: `git clone https://github.com/drshanali/portfolio.git`
2. Navigate to folder: `cd drshanali`
3. Start Python server: `python -m http.server 8000`
4. Open browser: `http://localhost:8000`

See [Setup Guide](setup.md) for details.

### Q: What do I need to install?

A: Minimal requirements:
- Git (for version control)
- Python 3.x (for local server)
- Modern web browser
- Code editor (VS Code recommended)

**No npm/Node.js needed!**

### Q: Where do I find documentation?

A: Documentation is in the `docs/` folder:
- `setup.md` - Setup instructions
- `architecture.md` - System design
- `features.md` - Feature list
- `deployment.md` - Deployment guide
- `security.md` - Security guide
- `performance.md` - Performance guide

### Q: What technologies does this use?

A: Pure web technologies:
- **HTML5** - Structure
- **CSS3** - Styling
- **Vanilla JavaScript** - Interactivity
- **No frameworks** - Pure browser APIs

---

## Deployment

### Q: How do I deploy the site?

A: Easiest way is Netlify:
1. Go to [netlify.com](https://netlify.com)
2. Click "New site from Git"
3. Connect GitHub repository
4. Click Deploy
5. Done! Site is live

See [Deployment Guide](deployment.md) for alternatives.

### Q: Does it cost to deploy?

A: No! All major platforms offer free hosting:
- **Netlify** - Free tier (unlimited sites)
- **Vercel** - Free tier (unlimited sites)
- **GitHub Pages** - Always free
- **AWS** - Free tier with limits

### Q: How do I use a custom domain?

A: After deployment:
1. Go to hosting platform domain settings
2. Add your domain name
3. Update DNS records at registrar
4. Wait 24 hours for propagation

### Q: Do I get SSL/HTTPS automatically?

A: Yes! All platforms provide:
- ✅ Automatic HTTPS
- ✅ Let's Encrypt certificates
- ✅ Auto-renewal
- ✅ No configuration needed

---

## Content & Pages

### Q: How do I add a new page?

A: Follow these steps:
1. Create new file: `pages/new-page.html`
2. Copy from similar existing page
3. Update content
4. Add navigation link in `index.html`
5. Test locally
6. Commit and push

### Q: How do I update page content?

A: Simple process:
1. Edit the `.html` file
2. Save changes
3. Refresh browser (F5)
4. Verify changes
5. Commit to Git
6. Push to GitHub
7. Auto-deploys

### Q: Can I add a blog?

A: Yes, framework is ready:
1. Create `blog/` directory
2. Add blog posts
3. Create blog index
4. Add navigation link
5. See `blog.js` for implementation

### Q: How do I add images?

A: Follow these steps:
1. Optimize image first (compress)
2. Place in `images/` folder
3. Add to HTML with `<img>` tag
4. Include alt text
5. Test that it displays
6. Commit changes

### Q: How do I change the site title or logo?

A: Update these files:
1. `index.html` - Change `<title>` tag
2. Add logo image to `images/`
3. Update `<header>` section
4. Update other pages as needed
5. Test across pages

---

## Technical

### Q: How do I modify CSS?

A: Edit `css/styles.css`:
1. Open in code editor
2. Find the section to modify
3. Update CSS rules
4. Refresh browser (Ctrl+Shift+R)
5. Test on mobile (F12 → Device)
6. Commit changes

**CSS Organization:**
- Root variables at top
- Component styles in middle
- Media queries at bottom
- Comments for sections

### Q: How do I add JavaScript functionality?

A: Modify or create `.js` file:
1. Edit or create file in `js/` folder
2. Use vanilla JavaScript APIs
3. Test in browser console (F12)
4. Add to HTML with `<script>` tag
5. Commit changes

**Best Practices:**
- Use event listeners
- Avoid inline scripts
- Comment complex code
- Test thoroughly

### Q: How do I manage responsive design?

A: Use CSS media queries:
```css
/* Mobile first */
.container { width: 100%; }

/* Tablet */
@media (min-width: 768px) {
  .container { width: 90%; }
}

/* Desktop */
@media (min-width: 1024px) {
  .container { width: 1200px; }
}
```

### Q: How do I add language translations?

A: Use i18n framework:
1. Edit `js/translations.js`
2. Add new language object
3. Use `i18n.js` for switching
4. Test language switcher
5. Commit changes

### Q: How does the contact form work?

A: Secure process:
1. Form validates in browser
2. Checks for required fields
3. Validates email format
4. Detects spam (honeypot)
5. Submits to FormSubmit.co
6. You receive email
7. User gets confirmation

---

## Performance

### Q: Why is my site slow?

A: Check these factors:
1. **Images** - Too large? Optimize with TinyJPG
2. **Network** - On slow connection? Test on 3G
3. **Browser** - Try different browser
4. **Cache** - Clear cache (Ctrl+Shift+Delete)
5. **Extensions** - Disable browser extensions

### Q: How do I optimize images?

A: Best practices:
- Use online tools: TinyJPG, TinyPNG
- Choose right format (JPG/PNG/SVG)
- Compress without quality loss
- Keep images < 200KB
- Use descriptive filenames

### Q: How do I test performance?

A: Free tools:
1. **Lighthouse** - F12 in Chrome
2. **PageSpeed Insights** - pagespeed.web.dev
3. **GTmetrix** - gtmetrix.com
4. **WebPageTest** - webpagetest.org

All show optimization tips.

### Q: What are Core Web Vitals?

A: Google's key metrics:
- **LCP** (Loading) - < 2.5s
- **FID** (Interactivity) - < 100ms
- **CLS** (Stability) - < 0.1

Our site: ✅ Excellent on all metrics

---

## Security & Privacy

### Q: Is my data safe?

A: Yes, multiple protections:
- ✅ HTTPS encryption
- ✅ Form validation
- ✅ Spam detection
- ✅ No data storage
- ✅ GDPR compliant

### Q: What data do you collect?

A: Form submission only:
- Name (optional)
- Email (required)
- Message (optional)

We **don't** collect:
- IP addresses
- Location data
- Browsing history
- Device information

### Q: Do you use cookies?

A: Only essential cookies:
- Language preference (if i18n enabled)
- Session management (form state)

We **don't** use:
- Tracking cookies
- Analytics cookies
- Third-party cookies

### Q: How is form data submitted?

A: Secure process:
1. Form validates locally
2. Submits to FormSubmit.co
3. You get email
4. No data stored on server
5. User gets confirmation

### Q: Is there a privacy policy?

A: Should be added:
1. Create `pages/privacy.html`
2. Detail data collection
3. Explain user rights
4. Link from footer
5. Keep updated

---

## Contributing

### Q: How do I contribute?

A: Follow these steps:
1. Fork repository
2. Create feature branch: `git checkout -b feature/my-feature`
3. Make changes
4. Commit: `git commit -m "feat: description"`
5. Push: `git push origin feature/my-feature`
6. Create Pull Request
7. Wait for review

See [CONTRIBUTING.md](../CONTRIBUTING.md) for details.

### Q: What's the code style?

A: Keep it simple:
- Clear variable names
- Comment complex code
- Semantic HTML
- Organized CSS (by component)
- Vanilla JavaScript

### Q: How do I report a bug?

A: Use GitHub Issues:
1. Go to GitHub repository
2. Click Issues tab
3. Click "New Issue"
4. Describe the problem
5. Include steps to reproduce
6. Add screenshots if helpful

### Q: Can I suggest features?

A: Yes! Create GitHub Discussion:
1. Go to Discussions tab
2. Click "New Discussion"
3. Describe feature
4. Explain use case
5. Wait for feedback

---

## Troubleshooting

### Q: Port 8000 is already in use

A: Try these solutions:
```bash
# Use different port
python -m http.server 8001

# Find and kill process (macOS/Linux)
lsof -i :8000
kill -9 <PID>

# Windows - Use Task Manager
# Find and close process
```

### Q: Images not loading

A: Check these:
1. **Paths** - Are image paths correct?
2. **Names** - Check file name case sensitivity
3. **Format** - Supported format (JPG/PNG/SVG)?
4. **Cache** - Clear browser cache
5. **Console** - Check for 404 errors (F12)

### Q: Form not submitting

A: Try these:
1. **Validation** - Are all required fields filled?
2. **Email** - Is email format valid?
3. **Spam** - Check honeypot field
4. **Network** - Check internet connection
5. **Console** - Look for error messages (F12)

### Q: Site not updating after push

A: Try these:
1. **Refresh** - Hard refresh (Ctrl+Shift+R)
2. **Cache** - Clear browser cache
3. **Build** - Check if deployment completed
4. **Logs** - Check platform build logs
5. **Wait** - Deployment takes ~1 minute

### Q: Links not working

A: Check:
1. **Path** - Is path correct? Use relative paths
2. **Case** - Check file name case
3. **Extension** - Include .html extension
4. **Trailing slash** - Avoid trailing slashes
5. **External** - External links need http://

### Q: Mobile view broken

A: Check:
1. **Viewport** - Is viewport meta tag present?
2. **Media queries** - Are breakpoints correct?
3. **Text** - Is text readable on mobile?
4. **Buttons** - Are buttons tap-friendly?
5. **Test** - Check with real device

### Q: Performance is slow

A: Try these:
1. **Images** - Compress images
2. **Cache** - Enable browser cache
3. **CDN** - Use CDN (Cloudflare)
4. **Network** - Test on different network
5. **Device** - Test on fast device

---

## Getting Help

### Resources

- 📖 **Documentation** - Start with docs/
- 🔍 **Search Issues** - Check GitHub Issues
- 💬 **Discussions** - Ask in GitHub Discussions
- 🐛 **Report Bugs** - Create GitHub Issue
- ✨ **Suggest Features** - Create Discussion

### Contact

- 📧 **Email** - Use contact form
- 🌐 **Website** - drshanali.com
- 🔗 **GitHub** - drshanali/portfolio

---

**Last Updated**: June 1, 2026  
**Status**: Comprehensive FAQ
