# 🚀 GitHub Setup & Deployment Guide for CricManager

Complete step-by-step instructions to set up your GitHub repository and deploy to GitHub Pages.

---

## ✅ Pre-Deployment Checklist

All project files are ready in `/Users/prabhsingh/Documents/Code/CricManager/`:

- ✅ `index.html` - Main application (66 KB)
- ✅ `README.md` - Project overview
- ✅ `LICENSE` - MIT license
- ✅ `.gitignore` - Git ignore rules
- ✅ `docs/FEATURES.md` - Feature documentation
- ✅ `docs/INSTALLATION.md` - Setup guide
- ✅ `docs/CSV_FORMAT.md` - CSV format specification
- ✅ `docs/CONTRIBUTING.md` - Contribution guidelines
- ✅ `docs/CHANGELOG.md` - Version history
- ✅ `samples/viewScorecardExcel.csv` - Test data
- ✅ `.github/workflows/pages.yml` - GitHub Pages deployment workflow

---

## Step 1: Create GitHub Repository

### On GitHub.com

1. **Go to**: https://github.com/new
2. **Repository name**: `CricManager` (exactly this)
3. **Description**: "Cricket match analyzer - CSV upload, player stats, team balancing, XI builder, and match cards with WhatsApp export"
4. **Visibility**: Select **"Public"**
5. **Initialize repository**:
   - ❌ Do NOT check "Add a README file"
   - ❌ Do NOT check "Add .gitignore"
   - ❌ Do NOT select a license
   - (We already have these files)
6. **Click**: "Create repository"

### After Creation

You'll see a page like this:
```
Quick setup — if you've done this kind of thing before

…or create a new repository on the command line
echo "# CricManager" >> README.md
git init
git add README.md
git commit -m "first commit"
...

…or push an existing repository from the command line
git remote add origin https://github.com/prabhsimransingh/CricManager.git
git branch -M main
git push -u origin main
```

**Copy this URL**: `https://github.com/prabhsimransingh/CricManager.git`

---

## Step 2: Initialize Local Git Repository

Open Terminal/Command Prompt:

### Windows (PowerShell)

```powershell
cd C:\Users\YourName\Documents\Code\CricManager
git init
git config user.name "Your Name"
git config user.email "your.email@example.com"
```

### macOS/Linux

```bash
cd /Users/prabhsingh/Documents/Code/CricManager
git init
git config user.name "Prabh Simran Singh"
git config user.email "your.email@example.com"
```

---

## Step 3: Add Remote and Initial Commit

### Add Remote Repository

```bash
git remote add origin https://github.com/prabhsimransingh/CricManager.git
git branch -M main
```

### Stage All Files

```bash
git add .
git status
```

**You should see** (git status output):
```
On branch main

No commits yet

Changes to be committed:
  new file:   .github/workflows/pages.yml
  new file:   .gitignore
  new file:   LICENSE
  new file:   README.md
  new file:   docs/CHANGELOG.md
  new file:   docs/CONTRIBUTING.md
  new file:   docs/CSV_FORMAT.md
  new file:   docs/FEATURES.md
  new file:   docs/INSTALLATION.md
  new file:   index.html
  new file:   samples/viewScorecardExcel.csv
```

### Create Initial Commit

```bash
git commit -m "Initial commit: CricManager v1.0.0

- Cricket match analyzer with 8 features
- CSV import from CricClubs format
- Player statistics and analytics
- Team split with intelligent balancing
- XI builder with smart player ordering
- Match card generation with WhatsApp export
- Full offline support via localStorage
- MIT licensed, open source"
```

### Verify Commit

```bash
git log --oneline
```

**You should see**:
```
abcd1234 Initial commit: CricManager v1.0.0
```

---

## Step 4: Push to GitHub

```bash
git push -u origin main
```

**First time**:
- May prompt for authentication
- On Windows: GitHub credentials helper
- On macOS/Linux: Personal access token or SSH

### Authentication Options

#### Option A: SSH (Recommended)
```bash
# If you have SSH key set up
git push -u origin main
# Should work without prompts
```

#### Option B: HTTPS with Personal Access Token
```bash
# Generate token on GitHub:
# 1. Settings → Developer settings → Personal access tokens
# 2. Click "Generate new token"
# 3. Check: repo (all), workflow
# 4. Copy token

# On first push, when prompted:
# Username: prabhsimransingh
# Password: [paste your token]
```

#### Option C: GitHub CLI
```bash
# Install: https://cli.github.com/
gh auth login
# Follow prompts
git push -u origin main
```

### Verify Push

```bash
git status
```

**Should show**:
```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

**On GitHub**: Refresh https://github.com/prabhsimransingh/CricManager
- Should see all files listed
- Should see 11 files total

---

## Step 5: Enable GitHub Pages

### In Repository Settings

1. **Go to**: https://github.com/prabhsimransingh/CricManager/settings
2. **Left menu**: Click "Pages" (or scroll down)
3. **Build and deployment**:
   - **Source**: Select "Deploy from a branch"
   - **Branch**: Select "main" dropdown
   - **Folder**: Select "/ (root)"
4. **Click**: "Save"

### Wait for Deployment

- GitHub Actions will run automatically
- Takes 30 seconds to 2 minutes
- You'll see a green checkmark next to the commit

### Check Deployment Status

1. **Go to**: https://github.com/prabhsimransingh/CricManager/actions
2. **Should see**: "pages build and deployment" workflow
3. **Status**: Should show green checkmark ✅

---

## Step 6: Verify Live Site

### Access Your Site

Open in browser:
```
https://prabhsimransingh.github.io/CricManager/
```

### Test Features

1. **Page loads**: HTML rendered correctly
2. **Upload works**: Try sample CSV
3. **Dashboard**: Shows match data
4. **All tabs**: Navigate through features
5. **Offline**: Works after first load

### If Page Doesn't Load

**Wait 1-2 minutes** for GitHub Pages to process, then refresh.

**Check Settings** → Pages section:
- Should show "Your site is published at..."

---

## Step 7: Add Repository Metadata

### Add Topics

1. **Go to**: https://github.com/prabhsimransingh/CricManager
2. **Right side**: Find "About" section
3. **Click gear icon**: Edit description
4. **Add topics** (comma-separated):
   ```
   cricket, analyzer, csv, web-app, open-source, sports-analytics
   ```
5. **Save**

### Update Repository Description

1. **Repository home page**
2. **Edit description**: "Cricket match analyzer with CSV import, player stats, team balancing, XI builder, and WhatsApp export"
3. **Save**

---

## Step 8: Create First Release (Optional but Recommended)

### GitHub Releases

1. **Go to**: https://github.com/prabhsimransingh/CricManager
2. **Right side**: Click "Releases" or "Create a release"
3. **Create new release**:
   - **Tag version**: `v1.0.0`
   - **Target**: `main`
   - **Release title**: `CricManager v1.0.0 - Initial Release`
   - **Description**:
     ```
     🎉 First stable release of CricManager!
     
     ## Features
     - 8 core features (Upload, Dashboard, Players, Trends, Partnerships, Team Split, XI Builder, Match Card)
     - CSV parsing from CricClubs format
     - Intelligent player role classification
     - Team balancing with snake-draft algorithm
     - Smart XI builder with optimal ordering
     - WhatsApp-ready match card export
     - Full offline support via localStorage
     - MIT licensed
     
     ## Download
     - [Live Demo](https://prabhsimransingh.github.io/CricManager/)
     - [Source Code](https://github.com/prabhsimransingh/CricManager)
     - [Documentation](docs/)
     
     ## Quick Start
     1. Open index.html in browser
     2. Upload cricket scorecard CSV (CricClubs format)
     3. Explore features
     4. Data saves offline automatically
     ```
   - **Attach binaries**: Upload `index.html` as asset
4. **Click**: "Publish release"

---

## Step 9: Verify Everything Works

### Checklist

- [ ] Repository created at github.com/prabhsimransingh/CricManager
- [ ] All files pushed to main branch
- [ ] GitHub Pages enabled in Settings
- [ ] Live site accessible at https://prabhsimransingh.github.io/CricManager/
- [ ] index.html loads without errors
- [ ] CSV upload works
- [ ] All features functional on live site
- [ ] Sample CSV available in samples/
- [ ] README displays correctly
- [ ] LICENSE shows "MIT" in UI
- [ ] Topics added to repository
- [ ] First release created (v1.0.0)

---

## 🎉 Deployment Complete!

### Your Site is Live!

**Live URL**: https://prabhsimransingh.github.io/CricManager/

**Repository**: https://github.com/prabhsimransingh/CricManager

---

## Next Steps

### Share Your Project

1. **GitHub**: Add to your profile/portfolio
2. **Social Media**:
   - "Just launched CricManager: An open-source cricket match analyzer! 🏏 Upload CSV, track players, build XIs. Check it out:"
   - Add link: https://prabhsimransingh.github.io/CricManager/
3. **Communities**:
   - Reddit: r/cricket, r/webdev
   - Dev.to: Write article about building it
   - GitHub: Add to your pinned repos

### Gather Feedback

1. Enable **GitHub Discussions** (Settings → Discussions)
2. Welcome **issues and PRs**
3. Respond to user feedback
4. Track feature requests

### Maintain the Project

1. Monitor GitHub Issues for bugs
2. Review pull requests from contributors
3. Update CHANGELOG for each release
4. Keep documentation current

---

## Troubleshooting

### "Repository not found" Error

**Cause**: Wrong URL or permission issue

**Solution**:
```bash
# Verify remote
git remote -v

# Should show:
# origin  https://github.com/prabhsimransingh/CricManager.git (fetch)
# origin  https://github.com/prabhsimransingh/CricManager.git (push)

# If wrong, fix it:
git remote set-url origin https://github.com/prabhsimransingh/CricManager.git
```

### "403 Forbidden" on Push

**Cause**: Authentication failed

**Solution**:
1. Check GitHub credentials
2. Verify personal access token (if using HTTPS)
3. Try SSH instead
4. Ensure you have write access

### GitHub Pages Not Updating

**Cause**: Cache or deployment delay

**Solution**:
```bash
# Force refresh
# Windows: Ctrl + Shift + Delete
# Mac: Cmd + Shift + Delete
# Then reload GitHub Pages URL
```

### Sample CSV Not Showing

**Cause**: File path issue

**Solution**:
1. Verify file is in `samples/viewScorecardExcel.csv`
2. Check git status: `git status samples/`
3. Re-add if needed: `git add samples/`
4. Commit and push

---

## Git Commands Reference

```bash
# Check status
git status

# See commit history
git log --oneline

# See what changed
git diff

# Add files
git add .

# Commit
git commit -m "message"

# Push to GitHub
git push

# Pull latest from GitHub
git pull

# Create new branch
git checkout -b feature-name

# Switch branches
git checkout branch-name

# Delete branch
git branch -d branch-name
```

---

## Security Notes

### GitHub Token Safety
- Never commit tokens to repository
- Use `.gitignore` to exclude sensitive files
- Rotate tokens periodically
- Check GitHub Security tab for alerts

### Protecting Your Repository
- Review collaborators regularly
- Enable branch protection (main branch)
- Require pull request reviews
- Monitor for suspicious activity

---

## Summary

✅ **Your open source project is now live!**

| Item | Status | URL |
|------|--------|-----|
| GitHub Repository | ✅ Live | https://github.com/prabhsimransingh/CricManager |
| GitHub Pages | ✅ Live | https://prabhsimransingh.github.io/CricManager/ |
| License | ✅ MIT | [LICENSE](LICENSE) |
| Documentation | ✅ Complete | [docs/](docs/) |
| Sample Data | ✅ Included | [samples/viewScorecardExcel.csv](samples/viewScorecardExcel.csv) |
| Contributing Guide | ✅ Ready | [docs/CONTRIBUTING.md](docs/CONTRIBUTING.md) |

---

## Get Help

- **Git Help**: https://git-scm.com/
- **GitHub Help**: https://docs.github.com/
- **GitHub Pages**: https://pages.github.com/
- **Markdown Guide**: https://www.markdownguide.org/

---

## Celebrating Your Launch! 🎉

You've successfully:
- ✅ Created an open source project
- ✅ Set up professional documentation
- ✅ Deployed to GitHub Pages
- ✅ Licensed with MIT
- ✅ Made it discoverable

**Welcome to open source!**

---

*Last Updated: April 30, 2026*

*Created with ❤️ by your AI assistant*
