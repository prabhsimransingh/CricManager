# 🏏 CricManager

> A lightweight, feature-rich cricket match analyzer with CSV import, player statistics, intelligent team balancing, and WhatsApp-ready match cards.

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![GitHub Repository](https://img.shields.io/badge/GitHub-CricManager-blue)](https://github.com/prabhsimransingh/CricManager)
[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-green)](https://prabhsimransingh.github.io/CricManager/)

## ✨ Features

### 📊 **Dashboard**
- Match overview and statistics
- Top batsmen and bowlers
- Quick performance metrics
- Match history tracker

### 👥 **Players Roster**
- Complete player listing with stats
- Filter by role (Batsman, Bowler, All-Rounder)
- Filter by team and form (hot/stable/cold)
- Search functionality
- Career statistics (runs, wickets, average, economy)

### 📈 **Trends & Analytics**
- Individual player performance tracking
- Last 5 match statistics
- Form indicators (hot/stable/cold)
- Batting and bowling charts
- Combined analytics for all-rounders

### 🤝 **Partnerships**
- Batting pair analysis
- Best cricket partnerships
- Shared match data
- Performance metrics

### 🏆 **Team Split**
- Intelligent player balancing
- Select 22, 24, or 26 players
- Snake-draft algorithm for fair distribution
- Role-based team composition
- Strength metrics and balance scoring

### 🎯 **XI Builder**
- Build 11, 12, or 13 player squads
- Smart player ordering
- Batting order (by powerplay avg, strike rate, form)
- Bowling order (by specialty, economy, wickets)
- Bowling rotation strategy

### 🖨️ **Match Card**
- Dual-team XI display
- Professional card formatting
- **WhatsApp export** with formatted lineup table
- Print-friendly layout
- Match metadata (date, time, venue)

### 🔒 **Offline Support**
- Full localStorage persistence
- Works completely offline
- Auto-save on CSV upload
- Auto-load on browser refresh

## 🚀 Quick Start

### Option 1: Use Live Demo (Easiest)
👉 **Open in browser:** [CricManager Live Demo](https://prabhsimransingh.github.io/CricManager/)

### Option 2: Run Locally
1. Download `index.html`
2. Open in any modern browser (Chrome, Firefox, Safari, Edge)
3. Done! ✓

### First Time Setup (5 Steps)
1. Open the application
2. Go to **Upload** tab
3. Choose your cricket scorecard CSV file (CricClubs format)
4. Click **"Upload & Parse"**
5. Explore features in the tabs above!

## 🌐 Community Scorecard Data

**Automatic Data Sharing** 📤

CricManager comes with built-in **community scorecard data**! 

- ✅ **Auto-loaded**: All CSV files in `/data/` directory load automatically
- ✅ **Shared data**: Every user sees all community scorecards
- ✅ **Works offline**: Bundled with the app, cached locally
- ✅ **Community-driven**: Users contribute matches via GitHub PRs

### How It Works
When you open CricManager, it automatically loads all scorecards from the `/data/` folder. No upload needed for community data—you get instant access to everyone's match data!

### Contribute Your Scorecard
Have a cricket match scorecard? Add it to the community!

1. **Export** your match from CricClubs as CSV
2. **Name it** clearly: `2026-MM-DD-team1-vs-team2.csv`
3. **Submit** a GitHub PR to add it to `/data/`
4. **Share** with everyone once merged!

👉 See [data/README.md](data/README.md) for detailed contribution guide.

### Example Community Data
- `2026-02-01-clinical-vs-surgical.csv` - Sample match included
- (Your matches here! 👈)

---

## 📋 CSV Format

CricManager accepts CSV exports from **CricClubs** in the following format:

```
Date: Team1 vs Team2 [winner info]

,,,Team1 Batting
BatsMan, How Out, Fielder, Bowler, Runs, Balls, Fours, Sixers
Player1, ct, Fielder1, Bowler1, 25, 30, 2, 1
...

,,,Team2 Bowling
Bowler, Overs, Maidens, Runs, Wickets, Wides, No Balls, Hattricks, Dot Balls
Bowler1, 4.0, 1, 28, 2, 1, 0, 0, 15
...
```

For detailed format documentation, see [CSV_FORMAT.md](docs/CSV_FORMAT.md)

## 💡 How It Works

### Data Parsing
- Parses CricClubs CSV scorecard format
- Extracts batting and bowling statistics
- Identifies player roles (Batsman, Bowler, All-Rounder)
- Calculates form based on last 5 matches

### Smart Features
- **Deduplication**: Re-uploading same CSV doesn't create duplicates
- **Form Calculation**: Hot/stable/cold based on recent performance
- **Team Balancing**: Snake-draft algorithm ensures fair team distribution
- **Smart Ordering**: Batsmen ordered by powerplay average → strike rate → form
- **Speciality Detection**: Identifies powerplay/middle/death specialists

### Data Storage
- All data stored in browser's **localStorage**
- ~2-5KB per cricket match
- Works offline once data is loaded
- No cloud sync or external API calls

## 🎮 Features Walkthrough

### 📊 Dashboard
View match summaries, top performers, and key statistics at a glance.

### 👥 Players
Search and filter all players by role, team, or form. View comprehensive career stats.

### 📈 Trends
Select a player to see their performance over last 5 matches with visual charts.

### 🤝 Partnerships
Discover the best batting partnerships and their combined performance.

### 🏆 Team Split
Intelligently split players into balanced teams for practice or friendly matches.

### 🎯 XI Builder
Build an optimal playing XI with smart batting and bowling order recommendations.

### 🖨️ Match Card
Create professional XI cards for both teams and export to WhatsApp.

## 🛠️ Technology Stack

- **Frontend**: Pure HTML5, CSS3, JavaScript (ES6+)
- **Charts**: Chart.js 3.9.1 (via CDN)
- **Storage**: Browser localStorage
- **Fonts**: Google Fonts (Syne, Outfit)
- **License**: MIT

**No external dependencies required** (except Chart.js CDN for charting)

## 🌐 Browser Support

| Browser | Version | Status |
|---------|---------|--------|
| Chrome/Chromium | Latest | ✅ Fully Supported |
| Firefox | Latest | ✅ Fully Supported |
| Safari | Latest | ✅ Fully Supported |
| Edge | Latest | ✅ Fully Supported |
| Internet Explorer | 11 | ❌ Not Supported |

## 📖 Documentation

- [**Features Guide**](docs/FEATURES.md) - Detailed feature documentation
- [**Installation**](docs/INSTALLATION.md) - Setup and deployment options
- [**CSV Format**](docs/CSV_FORMAT.md) - Scorecard CSV structure requirements
- [**Contributing**](docs/CONTRIBUTING.md) - How to contribute to the project
- [**Changelog**](docs/CHANGELOG.md) - Version history and releases

## 🤝 Contributing

We welcome contributions! Whether it's bug reports, feature requests, or code improvements:

1. **Report Issues**: [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues)
2. **Suggest Features**: Create an issue with label `enhancement`
3. **Submit Code**: Fork the repo and create a pull request

See [CONTRIBUTING.md](docs/CONTRIBUTING.md) for guidelines.

## 📝 Sample Data

A sample cricket scorecard is included in `/samples/viewScorecardExcel.csv`:
- **Match**: Clinical vs Surgical, Feb 1st 2026
- **Result**: Surgical won by 2 wickets
- **Players**: 23 total (15 All-Rounders, 5 Batsmen, 3 Bowlers)
- **Use Case**: Perfect for testing all features

## 🔧 Advanced Usage

### Keyboard Shortcuts
- `Ctrl/Cmd + Shift + R` - Hard refresh to clear cache
- `Ctrl/Cmd + S` - Print (when viewing Match Card)

### Offline Mode
1. Open CricManager online once
2. Upload your CSV file
3. Data is saved to localStorage
4. Can now use offline (all features except Chart.js CDN)

### Multiple Matches
Upload multiple CSV files from different dates to accumulate player statistics and see trend analysis.

### Data Backup
To backup your data:
1. Open browser DevTools (F12)
2. Console: `copy(JSON.stringify(localStorage))`
3. Paste into a text file

## 🐛 Troubleshooting

### Players showing wrong role?
- Clear database using "Clear Database" button in Upload tab
- Hard refresh page (Ctrl+Shift+R)
- Re-upload CSV

### Trends dropdown empty?
- Ensure CSV has been uploaded successfully
- Check console (F12) for errors
- Refresh page

### Charts not displaying?
- Ensure internet connection (Chart.js loads from CDN)
- Clear browser cache
- Try a different browser

See [Installation Guide](docs/INSTALLATION.md#troubleshooting) for more solutions.

## 📊 Data Privacy

✅ **Your data never leaves your browser**
- All processing happens locally
- No cloud storage or sync
- No external API calls
- No analytics or tracking

Data is stored only in your browser's localStorage. Clear it anytime using browser settings.

## 📜 License

This project is licensed under the MIT License - see [LICENSE](LICENSE) file for details.

### Attribution
- **Charts**: [Chart.js](https://www.chartjs.org) (Licensed under MIT)
- **Fonts**: [Google Fonts](https://fonts.google.com) (Licensed under Open Font License)

## 🙏 Credits

Created with ❤️ by [Prabh Simran Singh](https://github.com/prabhsimransingh)

## 🚀 Roadmap

Planned features for future releases:
- [ ] Multi-match aggregation improvements
- [ ] Export as PDF
- [ ] Dark mode
- [ ] Customizable team names and colors
- [ ] Performance analytics and predictions
- [ ] WebWorker for faster CSV parsing

## 💬 Feedback & Support

- **Questions?** Create an issue with label `question`
- **Bug Report?** File an issue with label `bug`
- **Feature Idea?** Create an issue with label `enhancement`
- **General Feedback?** Start a GitHub Discussion

## 📱 Social

- GitHub: [@prabhsimransingh](https://github.com/prabhsimransingh)
- Project: [CricManager Repo](https://github.com/prabhsimransingh/CricManager)

---

**Made with ❤️ for cricket analytics enthusiasts**

⭐ If you find CricManager useful, please star the repository!

---

*Last Updated: April 2026 | Version: 1.0.0*
