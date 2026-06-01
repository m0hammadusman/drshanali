# Installation & Setup Guide

Step-by-step guide to get the project running locally.

---

## Prerequisites

### Required
- Git
- Python 3.x
- Code editor (VS Code recommended)
- Modern web browser

### Optional
- Node.js (for alternative server)
- Command line knowledge

---

## Installation Steps

### Step 1: Clone Repository

```bash
# Using Git
git clone https://github.com/drshanali/portfolio.git

# Navigate to folder
cd portfolio
```

### Step 2: Verify Files

```bash
# Check important files exist
ls -la index.html css/ js/ pages/ images/

# Should see:
# index.html
# css/styles.css
# js/main.js
# pages/ directory
# images/ directory
```

### Step 3: Start Local Server

#### Option A: Python (Recommended)
```bash
# Python 3
python -m http.server 8000

# Or Python 2
python -m SimpleHTTPServer 8000
```

#### Option B: Node.js
```bash
# Install globally
npm install -g http-server

# Start server
http-server
```

#### Option C: VS Code Live Server
```
1. Open project in VS Code
2. Install "Live Server" extension
3. Right-click index.html
4. Select "Open with Live Server"
```

### Step 4: Open in Browser

- **Python**: http://localhost:8000
- **Node.js**: http://localhost:8080
- **Live Server**: Auto-opens

### Step 5: Verify Installation

- [ ] Homepage loads
- [ ] No console errors (F12)
- [ ] Navigation works
- [ ] Images display
- [ ] Mobile view responsive

---

## Project Structure

```
portfolio/
├── index.html              # Homepage
├── pages/                  # Content pages
│   ├── about.html
│   ├── practice-areas.html
│   ├── courses.html
│   └── ... (15 pages total)
├── css/
│   └── styles.css          # Main stylesheet
├── js/
│   ├── main.js             # Core JS
│   ├── contact.js          # Forms
│   ├── i18n.js             # Languages
│   ├── translations.js     # Strings
│   ├── blog.js             # Blog
│   └── tilt.js             # 3D effects
├── images/                 # 116 optimized images
├── docs/                   # Documentation
├── wiki/                   # Wiki pages
└── BUILD_SCRIPTS_ARCHIVE/  # Old scripts
```

---

## Development Workflow

### 1. Make Changes
- Edit HTML/CSS/JS files
- Save changes

### 2. Refresh Browser
- Ctrl+R (Windows/Linux)
- Cmd+R (macOS)
- Or browser refresh button

### 3. Check Console
- Press F12
- Go to Console tab
- Look for errors

### 4. Test Mobile
- F12 → Click device icon
- Select mobile view
- Test responsiveness

### 5. Commit Changes
```bash
# Stage changes
git add .

# Commit
git commit -m "feat: description of changes"

# Push
git push origin main
```

---

## VS Code Setup

### Recommended Extensions
1. Live Server
2. Prettier
3. ESLint
4. HTML CSS Support
5. Markdown Preview

### Install Extensions
```bash
# Via command palette
Ctrl+Shift+X

# Search for extension
# Click Install
```

### Useful Keyboard Shortcuts
- `Ctrl+K Ctrl+0` - Fold all
- `Ctrl+K Ctrl+J` - Unfold all
- `Ctrl+/` - Toggle comment
- `Ctrl+Shift+F` - Find in files
- `Alt+Up/Down` - Move line

---

## Common Issues

### Port Already in Use
```bash
# Try different port
python -m http.server 8001

# macOS/Linux - Find process
lsof -i :8000
kill -9 <PID>

# Windows - Use Task Manager
```

### Module Not Found
```bash
# Make sure you're in correct directory
cd portfolio

# Check Python version
python --version

# Try Python 3 explicitly
python3 -m http.server 8000
```

### Files Not Loading
```bash
# Check file paths
# Check case sensitivity
# Clear browser cache (Ctrl+Shift+Delete)
# Check console for 404 errors (F12)
```

### Form Not Working
```bash
# Check console (F12 → Console)
# Verify form elements present
# Check spam honeypot field
# Test on different browser
```

---

## Next Steps

1. **Explore Structure** - Read through HTML files
2. **Learn CSS** - Study styles.css organization
3. **Understand JS** - Review JavaScript modules
4. **Make Changes** - Edit content/styling
5. **Deploy** - Push changes to live site

---

## Resources

- [Main Docs](../docs/) - Full documentation
- [FAQ](../docs/faq.md) - Common questions
- [Architecture](Architecture.md) - Technical overview
- [Deployment](Deployment.md) - Hosting guide

---

**Last Updated**: June 1, 2026
