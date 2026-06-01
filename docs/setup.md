# Setup & Installation Guide

## Prerequisites

### System Requirements

- **OS**: Windows, macOS, or Linux
- **Git**: Version control system
- **Python**: 3.6+ (for local server)
- **Browser**: Modern browser (Chrome, Firefox, Safari, Edge)
- **Editor**: Code editor (VS Code recommended)

### Required Skills

- Basic HTML/CSS knowledge
- Basic JavaScript understanding
- Git fundamentals
- Command line basics

---

## Installation Steps

### Step 1: Clone Repository

```bash
# Using Git (Recommended)
git clone https://github.com/YOUR-USERNAME/drshanali.git
cd drshanali

# Or download ZIP
# Extract the ZIP file
# Navigate to the folder in terminal
```

### Step 2: Verify Installation

```bash
# Check all directories exist
ls -la  # macOS/Linux
dir     # Windows

# Should see:
# - index.html
# - css/
# - js/
# - pages/
# - images/
# - docs/
# - wiki/
```

### Step 3: Start Local Development

Choose one method:

#### Option A: Python HTTP Server (Recommended)

```bash
# Navigate to project folder
cd drshanali

# Start server with Python 3
python -m http.server 8000

# Start server with Python 2
python -m SimpleHTTPServer 8000

# Open browser
# http://localhost:8000
```

#### Option B: Node.js HTTP Server

```bash
# Install globally (if needed)
npm install -g http-server

# Start server
http-server

# Open browser
# http://localhost:8080
```

#### Option C: VS Code Live Server

```bash
# 1. Open project in VS Code
# 2. Install "Live Server" extension
# 3. Right-click index.html
# 4. Select "Open with Live Server"
# 5. Browser opens automatically
```

### Step 4: Verify Setup

- [ ] Homepage loads without errors
- [ ] Images display correctly
- [ ] Navigation links work
- [ ] Mobile view responsive (resize browser)
- [ ] No console errors (F12 → Console)
- [ ] Contact form visible

---

## Project Structure Overview

```
drshanali/
├── index.html              # Homepage
├── pages/                  # 15 content pages
├── css/                    # Styling
├── js/                     # JavaScript
├── images/                 # 116 images
├── docs/                   # Documentation
├── wiki/                   # Project wiki
└── BUILD_SCRIPTS_ARCHIVE/  # Deprecated scripts
```

---

## Development Environment Setup

### VS Code Extensions

**Essential Extensions:**
1. Live Server
2. Prettier - Code formatter
3. ESLint - JavaScript linter
4. HTML CSS Support
5. Markdown Preview

**Optional Extensions:**
- GitHub Copilot
- REST Client
- Thunder Client
- CSS Peek

### VS Code Settings

Create `.vscode/settings.json`:

```json
{
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "editor.formatOnSave": true,
  "editor.wordWrap": "on",
  "[html]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[css]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  }
}
```

### Git Configuration

```bash
# Set your name and email
git config --global user.name "Your Name"
git config --global user.email "your@email.com"

# Check configuration
git config --list
```

---

## First Changes Workflow

### 1. Create Feature Branch

```bash
# Update main branch
git checkout main
git pull origin main

# Create feature branch
git checkout -b feature/my-feature
```

### 2. Make Changes

```bash
# Edit files in editor
# Test changes in browser
# Verify no console errors
```

### 3. Test Changes

```bash
# Manual testing:
# 1. Click all links
# 2. Test form submission
# 3. Check mobile view (F12 → Device)
# 4. Verify images display
# 5. Check console for errors (F12 → Console)
```

### 4. Commit Changes

```bash
# Stage changes
git add .

# Commit with descriptive message
git commit -m "feat: add new feature description"

# Push to remote
git push origin feature/my-feature
```

### 5. Create Pull Request

```bash
# Go to GitHub
# Create Pull Request
# Describe changes
# Request review
# Merge when approved
```

---

## Troubleshooting Setup

### Issue: "Port Already in Use"

```bash
# Find what's using the port
# macOS/Linux:
lsof -i :8000

# Kill the process
kill -9 <PID>

# Or use a different port:
python -m http.server 8001
```

### Issue: "Module Not Found"

```bash
# Ensure you're in correct directory:
cd drshanali

# Verify Python installed:
python --version

# Try Python 3 explicitly:
python3 -m http.server 8000
```

### Issue: "Files Not Loading"

```bash
# Check file paths
# Verify relative paths are correct
# Check case sensitivity (Linux/Mac)
# Clear browser cache (Ctrl+Shift+Delete)
```

### Issue: "Permissions Denied"

```bash
# macOS/Linux - give execution permission:
chmod +x drshanali

# Or use sudo:
sudo python -m http.server 8000
```

---

## Next Steps

### 1. Explore Codebase

- [ ] Read `README.md` for overview
- [ ] Check `docs/architecture.md` for structure
- [ ] Review `docs/features.md` for capabilities
- [ ] Look at `CONTRIBUTING.md` for guidelines

### 2. Make Small Changes

- [ ] Edit page content
- [ ] Add an image
- [ ] Modify styling
- [ ] Test changes locally

### 3. Learn the Tools

- [ ] Understand HTML structure
- [ ] Learn CSS organization
- [ ] Study JavaScript files
- [ ] Review build scripts

### 4. Set Up Deployment

- [ ] Create Netlify account
- [ ] Connect GitHub repository
- [ ] Deploy website
- [ ] Test live site

---

## Performance Optimization

### Local Development

- Use Live Server for fast refresh
- Open DevTools (F12)
- Monitor Network tab
- Check Console for errors

### Testing

- Test on different devices
- Check responsive breakpoints
- Verify form submission
- Test all links

### Optimization

- Compress images (before adding)
- Minify code (if building)
- Enable caching (on server)
- Set up CDN (if needed)

---

## Common Tasks

### Adding a New Page

1. Create `pages/new-page.html`
2. Copy from similar page
3. Update content
4. Add navigation link
5. Test locally
6. Commit and push

### Updating Content

1. Edit HTML file
2. Test in browser
3. Check on mobile
4. Commit changes
5. Push to main

### Adding Images

1. Optimize image first
2. Place in `images/` folder
3. Add to HTML with alt text
4. Test loading
5. Commit

### Modifying Styles

1. Edit `css/styles.css`
2. Test on mobile
3. Check responsive breakpoints
4. Verify no layout shift
5. Commit changes

---

## Resources

### Documentation
- [Architecture Guide](../architecture.md)
- [Features List](../features.md)
- [Deployment Guide](../deployment.md)
- [FAQ](../faq.md)

### External Resources
- [MDN Web Docs](https://developer.mozilla.org)
- [CSS-Tricks](https://css-tricks.com)
- [Git Documentation](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com)

### Getting Help

- Check documentation first
- Search GitHub Issues
- Ask in GitHub Discussions
- Read Contributing guidelines

---

**Last Updated**: June 1, 2026  
**Status**: Ready for Development
