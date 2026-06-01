# Contributing Guidelines

Thank you for your interest in contributing to the Dr. Shan Ali professional portfolio website! This document outlines how to contribute.

## Getting Started

### Prerequisites

- Git installed
- Code editor (VS Code recommended)
- Python 3.x
- Basic HTML/CSS/JavaScript knowledge

### Setting Up

1. **Fork the Repository**
   - Click "Fork" on GitHub
   - Clone your fork locally

2. **Clone Locally**
   ```bash
   git clone https://github.com/YOUR-USERNAME/drshanali.git
   cd drshanali
   ```

3. **Create Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Code of Conduct

Please be respectful and professional:
- Be respectful of others' time and opinions
- Provide constructive feedback
- Focus on the issue, not the person
- Respect confidentiality (Dr. Shan Ali's personal information)

## Types of Contributions

### 1. Bug Reports

**Found a bug?** Create an issue with:
- Clear title
- Description of bug
- Steps to reproduce
- Expected vs actual behavior
- Screenshots if applicable

### 2. Feature Requests

**Suggest improvements:**
- What problem does it solve?
- How would it work?
- Are there alternatives?
- Potential impact

### 3. Code Contributions

**Follow these steps:**

1. **Create Feature Branch**
   ```bash
   git checkout -b feature/new-feature
   ```

2. **Make Changes**
   - Follow code style guide (see below)
   - Test thoroughly
   - Commit with clear messages

3. **Push to Fork**
   ```bash
   git push origin feature/new-feature
   ```

4. **Create Pull Request**
   - Describe changes
   - Reference related issues
   - Explain testing done

### 4. Documentation

- Fix typos
- Improve clarity
- Add examples
- Update outdated information

### 5. Content Updates

- Fix inaccuracies
- Update information
- Add new content
- Improve structure

## Development Workflow

### 1. Update Content

```bash
# Edit HTML file
vim pages/about.html

# Test locally
# Open in browser to verify changes

# Commit changes
git add pages/about.html
git commit -m "Update about page content"
```

### 2. Fix Styling

```bash
# Edit CSS file
vim css/styles.css

# Test on multiple browsers/devices

# Commit
git add css/styles.css
git commit -m "fix: improve mobile button styling"
```

### 3. Update JavaScript

```bash
# Edit JS file
vim js/main.js

# Test in browser console
# Verify no errors (F12 → Console)

# Commit
git add js/main.js
git commit -m "feat: add smooth scroll navigation"
```

## Code Style Guide

### HTML

```html
<!-- Use semantic elements -->
<header>
  <nav>Navigation</nav>
</header>

<main>
  <article>
    <h1>Main content</h1>
  </article>
</main>

<footer>
  Footer
</footer>

<!-- Indent 4 spaces -->
<div>
    <p>Indented</p>
</div>

<!-- Alt text for all images -->
<img src="image.jpg" alt="Descriptive text">
```

### CSS

```css
/* Use BEM-style naming */
.component { }
.component--variant { }
.component__element { }

/* Group related rules */
.button {
  padding: 10px 20px;
  background: var(--primary);
  color: var(--white);
  border: none;
  cursor: pointer;
  transition: all var(--transition);
}

.button:hover {
  background: var(--accent);
}

/* Mobile first */
@media (min-width: 768px) {
  .button {
    padding: 12px 24px;
  }
}
```

### JavaScript

```javascript
// Use camelCase for variables and functions
const userName = "John";
const calculateTotal = () => { };

// Use const by default, let if needed, avoid var
const permanentValue = "test";
let counter = 0;

// Comment complex logic
/*
 * Calculate total with tax
 * @param {number} subtotal
 * @returns {number} total with tax
 */
const calculateWithTax = (subtotal) => {
  const TAX_RATE = 0.1;
  return subtotal * (1 + TAX_RATE);
};

// Consistent error handling
try {
  const result = processData(input);
} catch (error) {
  console.error("Processing failed:", error);
}
```

## Testing Guidelines

### Before Submitting

**Content Changes:**
- [ ] Checked spelling and grammar
- [ ] Verified links work
- [ ] Images display correctly
- [ ] Mobile responsive
- [ ] No console errors

**Code Changes:**
- [ ] Code follows style guide
- [ ] No console errors (F12)
- [ ] Works on desktop and mobile
- [ ] Tested on Chrome, Firefox, Safari
- [ ] No performance degradation

**Security:**
- [ ] No sensitive data exposed
- [ ] Input properly validated
- [ ] No XSS vulnerabilities
- [ ] No broken links

### Running Local Tests

```bash
# Start local server
python -m http.server 8000

# Or use VS Code Live Server
# Right-click index.html → Open with Live Server

# Manually test
# - Click all links
# - Submit forms
# - Test on mobile device
# - Check console for errors
```

## Commit Message Format

```
<type>(<scope>): <subject>

<body>

<footer>
```

### Type
- `feat` - New feature
- `fix` - Bug fix
- `docs` - Documentation
- `style` - Code style (spacing, indentation)
- `refactor` - Code refactoring
- `test` - Adding tests
- `chore` - Maintenance

### Scope
- Component or area affected
- Examples: `navigation`, `contact-form`, `hero-section`

### Subject
- Imperative mood ("add" not "added")
- Lowercase first letter
- No period at end
- Max 50 characters

### Body
- Explain what and why
- Reference issues: `Closes #123`
- Wrap at 72 characters

### Example

```
feat(contact-form): add email validation

Implement client-side email validation using regex pattern.
Prevents invalid submissions and improves UX.

- Add validateEmail() function
- Display error message for invalid emails
- Add visual feedback for form validation

Closes #45
```

## Pull Request Process

### Before Submitting PR

1. **Update your branch**
   ```bash
   git fetch origin
   git rebase origin/main
   ```

2. **Test thoroughly**
   - All changes working
   - No console errors
   - Tested on multiple browsers

3. **Review your changes**
   ```bash
   git diff main
   ```

### Creating PR

1. **Push to Fork**
   ```bash
   git push origin feature/your-feature
   ```

2. **Create Pull Request**
   - Go to GitHub
   - Click "Compare & pull request"
   - Fill in template:

```markdown
## Description
Brief description of changes

## Type of Change
- [ ] Bug fix
- [ ] New feature
- [ ] Documentation
- [ ] Content update

## How to Test
Steps to verify changes work

## Screenshots (if applicable)
Add screenshots showing before/after

## Checklist
- [ ] Code follows style guide
- [ ] No console errors
- [ ] Tested on multiple browsers
- [ ] Documentation updated
- [ ] Commits messages clear
```

### During Review

- Respond to feedback promptly
- Make requested changes
- Push updates (PR automatically updates)
- Be respectful and open to suggestions

## Issue Labels

- **`bug`** - Something not working
- **`enhancement`** - New feature request
- **`documentation`** - Documentation update
- **`help wanted`** - Needs community help
- **`good first issue`** - Good for beginners
- **`high priority`** - Important, tackle first

## Release Process

Releases follow semantic versioning (MAJOR.MINOR.PATCH):

- **MAJOR** - Breaking changes
- **MINOR** - New features (backward compatible)
- **PATCH** - Bug fixes

### Creating a Release

1. Update version in documentation
2. Create release notes (CHANGELOG.md)
3. Create git tag
4. Deploy to production

## Community

### Getting Help

- **Documentation**: Check README.md, DEVELOPMENT.md
- **Issues**: Search existing issues
- **Discussions**: Ask questions respectfully
- **Email**: For urgent matters

### Recognized Contributors

Contributors will be:
- Added to CONTRIBUTORS.md
- Mentioned in release notes
- Thanked in documentation

## Contact

- **Email**: [Add contact email]
- **GitHub Issues**: For bug reports and features
- **Discussions**: For general questions

## Additional Resources

- [Development Guide](DEVELOPMENT.md) - Setup and workflow
- [Architecture Guide](ARCHITECTURE.md) - System design
- [Git Workflow](https://guides.github.com) - Git tutorials
- [Markdown Guide](https://www.markdownguide.org) - Markdown help

---

**Thank you for contributing!**

Your efforts help make this project better for everyone.

**Last Updated**: June 1, 2026
