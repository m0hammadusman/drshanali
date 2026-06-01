# Troubleshooting Guide

Solutions to common problems.

---

## Setup Issues

### Q: "Command not found: python"

**Solutions:**
```bash
# Check if Python is installed
python --version

# Try Python 3
python3 --version

# If not installed, download from python.org

# macOS - use Homebrew
brew install python3

# Windows - Download from python.org
```

### Q: Port 8000 Already in Use

**Solutions:**
```bash
# Use different port
python -m http.server 8001

# macOS/Linux - Find and kill process
lsof -i :8000
kill -9 <PID>

# Windows - Use Task Manager
1. Open Task Manager
2. Find Python process
3. Click End Task
```

### Q: "Permission Denied" (macOS/Linux)

**Solutions:**
```bash
# Give execute permission
chmod +x portfolio

# Or use sudo
sudo python -m http.server 8000
```

---

## File & Path Issues

### Q: "Cannot find images"

**Solutions:**
1. Check image paths are correct
2. Verify case sensitivity (Linux/Mac)
3. Clear browser cache (Ctrl+Shift+Delete)
4. Check console (F12 → Console) for 404 errors

**Example:**
```html
<!-- ✅ CORRECT -->
<img src="images/photo.jpg" alt="Photo" />

<!-- ❌ INCORRECT -->
<img src="/images/photo.jpg" alt="Photo" />
<img src="../images/photo.jpg" alt="Photo" />
```

### Q: Links Not Working

**Check:**
- [ ] Path is relative
- [ ] File name correct (case-sensitive)
- [ ] Extension included (.html)
- [ ] No extra slashes
- [ ] External links have http://

**Example:**
```html
<!-- ✅ CORRECT -->
<a href="pages/about.html">About</a>

<!-- ❌ INCORRECT -->
<a href="/pages/about.html">About</a>
<a href="pages/about">About</a>
```

---

## Browser Issues

### Q: "Page Not Loading" or "ERR_INVALID_URL"

**Solutions:**
1. Check URL: http://localhost:8000
2. Verify server is running
3. Check console (F12)
4. Try different port: http://localhost:8001
5. Check file exists: index.html

### Q: "CSS Not Applied" or Styles Look Wrong

**Solutions:**
```bash
# Hard refresh browser
Ctrl+Shift+R (Windows/Linux)
Cmd+Shift+R (macOS)

# Or clear cache
F12 → Settings → Clear browser cache

# Check CSS file loads
F12 → Network tab → Look for styles.css
```

### Q: JavaScript Not Working

**Solutions:**
1. Open DevTools (F12)
2. Go to Console tab
3. Look for error messages
4. Check syntax in .js files
5. Verify script tags in HTML:

```html
<!-- ✅ CORRECT -->
<script src="js/main.js"></script>

<!-- ❌ INCORRECT -->
<script>js/main.js</script>
<script src="js/main.js></script>
```

### Q: "Mobile View Broken"

**Solutions:**
1. Check viewport meta tag exists
2. Test with actual device
3. F12 → Device toggle
4. Try different screen sizes
5. Check media queries

**Meta tag:**
```html
<!-- ✅ CORRECT -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

---

## Form Issues

### Q: Contact Form Not Submitting

**Solutions:**
1. Check all required fields filled
2. Verify email format (name@domain.com)
3. Look for form validation errors
4. Check console (F12) for errors
5. Check honeypot field (shouldn't be visible)

**Test:**
```bash
# Fill out form with valid data
# Check Network tab (F12) for request
# Should see POST to formsubmit.co
```

### Q: Form Validation Not Working

**Solutions:**
1. Check contact.js loaded
2. Verify form has correct structure
3. Check for JavaScript errors (F12)
4. Test with empty fields
5. Test with invalid email

---

## Performance Issues

### Q: "Site is Slow"

**Check:**
- [ ] Network speed (F12 → Network)
- [ ] Image sizes (Right-click → Inspect)
- [ ] Too many requests (F12 → Network)
- [ ] Large files (> 1MB?)
- [ ] Browser extensions (disable)

**Solutions:**
1. Compress images
2. Clear browser cache
3. Try different browser
4. Test on different network
5. Check for slow assets (F12)

### Q: Images Loading Slowly

**Solutions:**
1. Compress images (TinyJPG, etc.)
2. Use appropriate format (JPG/PNG/SVG)
3. Enable lazy loading
4. Use CDN (optional)
5. Check image sizes

---

## Git Issues

### Q: "Git not found"

**Solutions:**
```bash
# Install Git
# Windows: git-scm.com
# macOS: brew install git
# Linux: sudo apt install git

# Verify installation
git --version
```

### Q: "Changes not committing"

**Solutions:**
```bash
# Stage all changes
git add .

# Or stage specific files
git add <filename>

# Check status
git status

# Commit
git commit -m "Description"

# Push
git push origin main
```

### Q: "Merge conflicts"

**Solutions:**
1. Open file with conflicts
2. Find conflict markers (`<<<<<<<`, `=======`, `>>>>>>>`)
3. Choose which code to keep
4. Remove markers
5. Commit changes

---

## Deployment Issues

### Q: "Site Not Updating After Push"

**Solutions:**
1. Verify commit pushed: `git log`
2. Check deployment status on Netlify/Vercel
3. Hard refresh browser (Ctrl+Shift+R)
4. Clear browser cache
5. Wait 1-2 minutes
6. Check build logs for errors

### Q: "SSL Certificate Error"

**Solutions:**
- Should be automatic (no action needed)
- Wait 10 minutes
- Try different browser
- Clear SSL cache
- Contact support if persists

### Q: "404 on Live Site"

**Solutions:**
1. Check file exists locally
2. Verify file was committed
3. Check deployment completed
4. Hard refresh browser
5. Check console (F12)

---

## SEO Issues

### Q: "Google Not Indexing Site"

**Solutions:**
1. Add to Google Search Console
2. Submit sitemap
3. Check robots.txt
4. Verify noindex not set
5. Wait for indexing

### Q: "Meta Tags Not Showing"

**Solutions:**
1. Use [https://www.opengraph.xyz/](https://www.opengraph.xyz/)
2. Check source code for meta tags
3. Verify format correct
4. Wait for social cache clear

---

## Console Errors

### Common Error Messages

**"Uncaught TypeError"**
- Check variable names
- Verify function exists
- Check syntax

**"404 Not Found"**
- File not found
- Wrong path
- Wrong filename

**"Failed to fetch"**
- CORS issue
- File not accessible
- Network problem

**Solution:**
1. Note error message
2. Find line number
3. Edit file
4. Refresh browser

---

## Getting Help

### Resources

1. **Read Docs** - Check [docs/](../docs/) first
2. **Check FAQ** - See [FAQ](../docs/faq.md)
3. **Search Issues** - GitHub Issues
4. **Ask Community** - GitHub Discussions
5. **Read Error** - Check console carefully

### Where to Report

**Bugs**: Create GitHub Issue  
**Questions**: GitHub Discussions  
**Feature Requests**: GitHub Discussions  
**Security**: Email security@drshanali.com

---

## Prevention Tips

1. **Test Locally First**
   - Make changes
   - Test in browser
   - Check mobile view
   - Check console

2. **Commit Often**
   - Small, focused commits
   - Clear commit messages
   - Easy to track changes

3. **Monitor After Deploy**
   - Check live site
   - Test all links
   - Monitor performance
   - Check analytics

4. **Keep Backups**
   - Use Git (automatic)
   - Tag releases
   - Document changes

---

## Still Stuck?

1. Check this guide thoroughly
2. Read [FAQ](../docs/faq.md)
3. Check [Architecture](Architecture.md)
4. Search online for error
5. Ask on GitHub Discussions
6. Email support

---

**Last Updated**: June 1, 2026
