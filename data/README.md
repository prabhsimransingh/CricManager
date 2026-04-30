# 🏏 Community Scorecard Data

This directory contains cricket match scorecards that are **automatically loaded when you open CricManager**. 

All users benefit from this shared community data - everyone sees all scorecards!

---

## 📊 Available Scorecards

### Clinical vs Surgical (Feb 1, 2026)
- **File**: `2026-02-01-clinical-vs-surgical.csv`
- **Result**: Surgical won by 2 wickets
- **Players**: 23 total (15 All-Rounders, 5 Batsmen, 3 Bowlers)
- **Use**: Sample data for testing all features

*Add your match data here! ⬇️*

---

## 🤝 Contributing Your Scorecard

Want to add your cricket match data to CricManager? It's easy!

### Step 1: Export Your Scorecard
1. Go to [CricClubs](https://www.cricclubs.com/)
2. Find your match
3. Click "Export" or "Download Scorecard"
4. Select **"Excel CSV"** format
5. Save the file

### Step 2: Name Your File
Use this format: `YYYY-MM-DD-team1-vs-team2.csv`

**Examples**:
- `2026-03-15-delhi-vs-mumbai.csv`
- `2026-03-20-city-vs-suburbs.csv`
- `2026-04-01-tournament-final.csv`

**Good naming**:
- ✅ Clear date (YYYY-MM-DD)
- ✅ Team names (lowercase, no spaces)
- ✅ Underscore between words

**Avoid**:
- ❌ `match1.csv` (no date/teams)
- ❌ `clinical vs surgical.csv` (spaces)
- ❌ `My_Match_from_March.csv` (unclear date)

### Step 3: Add to Repository

**Option A: Using GitHub Web (Easiest)**
1. Go to: https://github.com/prabhsimransingh/CricManager/tree/main/data
2. Click "Add file" → "Upload files"
3. Drag your CSV file
4. Commit with message: "Add scorecard: [match details]"

**Option B: Using Git (For Developers)**
```bash
# Clone the repo
git clone https://github.com/prabhsimransingh/CricManager.git
cd CricManager/data

# Copy your CSV here
cp ~/Downloads/your-match.csv ./2026-MM-DD-team1-vs-team2.csv

# Commit
git add .
git commit -m "Add scorecard: Team1 vs Team2 on 2026-MM-DD"

# Push
git push origin main
```

### Step 4: Create Pull Request
1. If using GitHub web: Automatically creates PR
2. If using Git: Push and create PR from your fork
3. Add description of the match (optional but nice!)
4. Submit PR

### Step 5: Done! 🎉
Once approved and merged:
- ✅ Your match data loads for **everyone**
- ✅ Appears in all users' Dashboard
- ✅ Players get aggregated stats across matches
- ✅ Community data grows!

---

## 📋 CSV Format Requirements

Your CSV must follow the **CricClubs export format**:

### Structure
```
Header: Date and match result info
Team line: Team1 vs Team2
[blank line]

,,,Team1 Batting
Column headers
[player data rows]
[summary/totals]

,,,Team2 Bowling
Column headers
[player data rows]
[summary/totals]

,,,Team2 Batting
[same structure]

,,,Team1 Bowling
[same structure]
```

### Validation
- ✅ 4 sections: Team1 Batting, Team2 Bowling, Team2 Batting, Team1 Bowling
- ✅ Proper column headers
- ✅ Player names consistent across sections
- ✅ Numbers valid (no letters in numeric columns)
- ✅ UTF-8 encoding (default)

**Not sure?** Download any match from CricClubs and use it as a template!

See [CSV_FORMAT.md](../docs/CSV_FORMAT.md) for detailed specifications.

---

## ✅ Quality Guidelines

**Before submitting, ensure**:

- [ ] File is valid CSV from CricClubs
- [ ] Filename format: `YYYY-MM-DD-team1-vs-team2.csv`
- [ ] No duplicate files (check existing names first)
- [ ] File size < 100 KB
- [ ] No sensitive personal data in filename
- [ ] Tested: CricManager loads it without errors

---

## 🔄 How It Works

When you open CricManager:
1. **Page loads** from GitHub Pages
2. **JavaScript fetches** all CSVs from `/data/` folder
3. **Parses all scorecards** automatically
4. **Merges into database** (local + community data)
5. **Shows on Dashboard** - no upload needed!
6. **Works offline** - data cached in localStorage

---

## 📈 Community Statistics

**Current Data**:
- Total matches: See Dashboard
- Total players: See Dashboard
- Total scorecards: Check this folder!

**Your contribution adds to these totals!**

---

## ❓ FAQ

### Q: Will my data be shared?
**A**: Yes! That's the point. Once merged, everyone using CricManager sees your data. Great for building a community cricket database!

### Q: Can I add matches from other sources?
**A**: Only CricClubs format supported. The CSV must have the exact structure.

### Q: What if I want to remove my data?
**A**: Open an issue or make a PR removing the file. We respect your privacy!

### Q: How often is data updated?
**A**: Immediately when merged. Next time someone visits CricManager, they see new data.

### Q: Can I add multiple files at once?
**A**: Yes! Upload multiple CSVs in one PR. Name each clearly.

### Q: What if my match data is from an old CricClubs export?
**A**: Should still work! CricClubs format is stable. If issues, mention in PR description.

---

## 🚀 Examples

### Example 1: Weekend Friendly Match
```
File: 2026-04-05-alpha-vs-beta.csv
Match: Alpha team vs Beta team
Date: April 5, 2026
Result: Alpha won
```

### Example 2: Tournament Match
```
File: 2026-04-10-tournament-semifinal.csv
Match: TeamA vs TeamB
Tournament: Spring Championship
```

### Example 3: Family Match
```
File: 2026-04-12-family-west-vs-east.csv
Match: Family West XI vs Family East XI
Casual match, tracking family players
```

---

## 📞 Support

- **Questions?** Open an [issue](https://github.com/prabhsimransingh/CricManager/issues)
- **Problems?** Check [CSV_FORMAT.md](../docs/CSV_FORMAT.md)
- **Want to help?** See [CONTRIBUTING.md](../docs/CONTRIBUTING.md)

---

## 🏆 Contributors

Thank you to everyone contributing scorecard data! Your matches help build a collaborative cricket analytics platform.

**Contributed by**:
- Sample data: Initial repository

*Add your name here! Submit a scorecard and be part of the community.* 🙌

---

*This directory grows with community contributions. Help build the cricket analytics knowledge base!*

---

**Last Updated**: April 30, 2026  
**Total Scorecards**: Count from folder!  
**Help**: See [CONTRIBUTING.md](../docs/CONTRIBUTING.md)
