# 🤝 Contributing to CricManager

Thank you for considering contributing to CricManager! We welcome all types of contributions.

---

## Types of Contributions

### 🐛 Bug Reports
Found a bug? Help us fix it!

**How to report**:
1. Go to [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues)
2. Click "New Issue"
3. Title: Brief description of bug
4. Description:
   - What were you doing?
   - What happened?
   - What should have happened?
   - Browser/OS info
   - Steps to reproduce

**Example**:
```
Title: CSV upload fails with CricClubs export

Description:
- Browser: Chrome 120
- OS: Windows 11
- Steps:
  1. Download CSV from CricClubs
  2. Click Upload tab
  3. Select CSV file
  4. Click "Upload & Parse"
  5. Error: "Teams not found"
```

### 💡 Feature Requests
Have an idea? Suggest it!

**How to request**:
1. Go to [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues)
2. Click "New Issue"
3. Label: "enhancement"
4. Title: Feature name
5. Description:
   - What problem does it solve?
   - How should it work?
   - Example use case
   - Any relevant screenshots/mockups

**Example**:
```
Title: Add dark mode for night usage

Description:
Dark mode would help users at night and reduce eye strain.
Could add toggle in settings to switch between light/dark themes.
```

### 🏏 Scorecard Data
Help build our community cricket database!

**How to contribute**:
1. Export your match scorecard from [CricClubs](https://www.cricclubs.com/) as CSV
2. Name the file clearly: `YYYY-MM-DD-team1-vs-team2.csv`
   - Example: `2026-04-15-delhi-vs-mumbai.csv`
3. Fork the repo and add your CSV to the `data/` directory
4. Submit a pull request with match details

**Why contribute?**
- ✅ Your match data becomes available to all CricManager users
- ✅ Build a collaborative cricket analytics knowledge base
- ✅ Help others analyze cricket trends
- ✅ Contribute to the community cricket movement

**Example**:
```
File: 2026-04-20-alpha-vs-beta.csv
Match: Alpha team vs Beta team
Date: April 20, 2026
Players: 22 players (all-rounders, batsmen, bowlers)
```

**Full Guide**: See [data/README.md](../data/README.md) for detailed instructions on:
- Exporting from CricClubs
- File naming conventions
- CSV format requirements
- Quality guidelines
- FAQ

### 📝 Documentation
Help us improve docs!

**How to contribute**:
1. Find outdated/unclear documentation
2. Fork the repo (or edit directly on GitHub)
3. Make improvements
4. Submit pull request with description

**Ideas**:
- Clarify confusing sections
- Add examples
- Fix typos
- Add FAQ entries
- Add screenshots

### 💻 Code Improvements
Want to improve the code?

**Before you start**:
1. Check [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues) for planned work
2. Comment on issue to let others know you're working on it
3. Fork the repo
4. Make changes in a new branch

**Guidelines**:
- One feature per pull request
- Write clear commit messages
- Update documentation if needed
- Test thoroughly before submitting

---

## Development Setup

### Requirements
- Git
- Text editor or IDE (VS Code recommended)
- Modern web browser
- Python 3.x (optional, for local server)

### Steps

1. **Fork the repository**
   ```bash
   # Go to https://github.com/prabhsimransingh/CricManager
   # Click "Fork" button
   ```

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/CricManager.git
   cd CricManager
   ```

3. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   # Or for bugs:
   git checkout -b fix/bug-description
   ```

4. **Make your changes**
   - Edit `index.html` for code changes
   - Edit files in `docs/` for documentation
   - Test thoroughly in browser

5. **Test your changes**
   ```bash
   # Option 1: Direct open
   # Open index.html in browser
   
   # Option 2: Local server (recommended)
   python -m http.server 8000
   # Visit http://localhost:8000/
   ```

6. **Commit your changes**
   ```bash
   git add .
   git commit -m "Clear description of your change"
   ```

   **Good commit messages**:
   ```
   Add dark mode toggle to settings
   Fix CSV parsing for Team names with spaces
   Update INSTALLATION.md with troubleshooting
   ```

   **Avoid**:
   ```
   fixed stuff
   changes
   asdf
   ```

7. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

8. **Create Pull Request**
   - Go to [CricManager](https://github.com/prabhsimransingh/CricManager)
   - Click "New Pull Request"
   - Select your branch
   - Fill in description
   - Submit!

---

## Code Style Guide

### JavaScript
- Use **ES6+ syntax** (arrow functions, const/let, etc.)
- Use **camelCase** for variables: `cricketPlayers`, `csvData`
- Use **UPPERCASE** for constants: `MAX_PLAYERS`, `DEFAULT_FORMAT`
- Comment complex logic with **inline comments**
- Keep functions **focused and small**

### HTML
- Use **semantic HTML5** elements
- Add **descriptive IDs and classes**
- Use **data attributes** for JavaScript hooks
- Keep **indentation consistent** (2 spaces)

### CSS
- Use **CSS variables** for colors (already in place)
- Keep **specificity low** (avoid nested selectors)
- Use **CSS Grid and Flexbox** for layouts
- Add **comments** for sections
- Mobile-first approach

### Examples

**Good**:
```javascript
// Calculate player form based on recent performance
const calculateForm = (player) => {
  const recentRuns = player.last_5.slice(-2).reduce((s, m) => s + m.runs, 0);
  return recentRuns > 15 ? 'hot' : recentRuns < -20 ? 'cold' : 'stable';
};
```

**Avoid**:
```javascript
// bad variable names and no comments
const cf = p => {
  const r = p.last_5.slice(-2).reduce((s, m) => s + m.runs, 0);
  return r > 15 ? 'h' : r < -20 ? 'c' : 's';
};
```

---

## Testing Your Changes

### Manual Testing Checklist

- [ ] **Upload CSV**: Test with sample CSV
- [ ] **All Tabs**: Navigate to each tab
- [ ] **Features**: Test your specific change
- [ ] **Offline**: Refresh page (data persists)
- [ ] **Browsers**: Test in Chrome, Firefox, Safari
- [ ] **Mobile**: Test on mobile screen size
- [ ] **Console**: No errors in DevTools (F12)
- [ ] **Performance**: Page loads quickly

### Testing a Feature Change
```javascript
// Example: If you change player ordering

1. Go to XI Builder
2. Select 11 players
3. Click "Smart Order"
4. Verify batsmen ordered correctly:
   - Check powerplay_avg DESC
   - Check strike_rate DESC
   - Check form priority
5. Verify bowlers ordered correctly:
   - Check specialty (PP → M → D)
   - Check economy ASC
   - Check wickets DESC
6. Test in different browsers
```

---

## Pull Request Process

### What to Include
1. **Clear title** describing change
2. **Detailed description** of what changed and why
3. **Testing notes** - what you tested
4. **References** - link to related issues
5. **Screenshots** - if applicable

### Pull Request Template
```markdown
## Description
What changes did you make?

## Related Issue
Fixes #123 (GitHub issue number)

## Testing
How did you test this?
- [ ] Tested in Chrome
- [ ] Tested in Firefox
- [ ] Tested on mobile
- [ ] All features working

## Screenshots (if applicable)
Before/after screenshots

## Checklist
- [ ] Code follows style guide
- [ ] Updated documentation
- [ ] No console errors
- [ ] Tested thoroughly
```

### Review Process
- Maintainer will review your PR
- May request changes or clarifications
- Once approved, will be merged
- Thank you for contributing!

---

## Area-Specific Guidelines

### CSV Parsing Improvements
- Changes to `parseOneCSV()`, `parseBatSec()`, `parseBowlSec()`
- Test with multiple CSV formats
- Ensure backwards compatibility
- Document new format support

### Feature Additions
- Add to appropriate tab section
- Update FEATURES.md documentation
- Ensure offline compatibility
- Test localStorage persistence

### UI/UX Changes
- Maintain responsive design
- Test on mobile (375px width)
- Ensure accessibility
- Keep visual consistency

### Performance Improvements
- Profile before/after (DevTools)
- Minimize localStorage access
- Avoid unnecessary DOM manipulations
- Test with large data (100+ players)

---

## Documentation Standards

### For Code Changes
```javascript
// ════════════════════════════════════════════
// FEATURE NAME (section header)
// ════════════════════════════════════════════

/**
 * Brief description of what function does
 * @param {type} paramName - Description
 * @return {type} Description of return value
 */
function myFunction(paramName) {
  // Implementation
}
```

### For Markdown Files
- Use **clear headings** hierarchy (# ## ###)
- Add **table of contents** for long docs
- Include **code examples**
- Add **emoji** for visual breaks
- Link to **related docs**

### For Commit Messages
```
[Type] Brief description

Detailed explanation of changes, why they were made,
and any relevant context. Reference issue #123.
```

**Types**: fix, feat, docs, refactor, perf, test

---

## Communication

### Questions or Discussions
- [GitHub Discussions](https://github.com/prabhsimransingh/CricManager/discussions) (coming soon)
- [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues) with label "question"
- Be respectful and constructive

### Code Review
- Reviews are supportive, not critical
- Aim to improve code quality together
- Ask questions if you don't understand feedback
- Everyone's learning!

---

## Recognition

Contributors are recognized:
- Listed in [CHANGELOG.md](CHANGELOG.md) for releases
- Mentioned in GitHub
- Big thanks for your time and effort!

---

## Code of Conduct

All contributors are expected to:
- ✅ Be respectful and inclusive
- ✅ Provide constructive feedback
- ✅ Accept criticism gracefully
- ✅ Focus on the work, not the person
- ❌ Avoid harassment, discrimination, or hate speech

---

## Legal

By contributing to CricManager, you agree:
- Your contribution is under MIT license
- You have rights to contribute the code
- You won't breach others' intellectual property

---

## Roadmap

Planned improvements (help needed!):
- [ ] Multi-match aggregation UI
- [ ] PDF export
- [ ] Dark mode
- [ ] Advanced statistics
- [ ] Performance optimizations
- [ ] More export formats

Interested in any of these? Comment on [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues)!

---

## Questions?

- **Technical Help**: Comment on issue or PR
- **General Questions**: GitHub Issues with "question" label
- **Want to Discuss**: Start a GitHub Discussion

---

## Thank You! 🙏

Your contributions make CricManager better for everyone.

Whether it's code, docs, bug reports, or feature ideas - **all help is appreciated!**

---

*Last Updated: April 2026*
