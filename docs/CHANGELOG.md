# 📝 Changelog

All notable changes to CricManager are documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/), and this project adheres to [Semantic Versioning](https://semver.org/).

---

## [Unreleased]

### Planned Features
- [ ] Dark mode support
- [ ] PDF export for match cards
- [ ] Advanced multi-match statistics
- [ ] Customizable team colors
- [ ] Performance predictions
- [ ] WebWorker for faster CSV parsing
- [ ] Additional export formats (JSON, XML)

### Known Issues
- Chart.js requires CDN on first load (no offline charts on first use)
- Form calculation needs 4+ matches for accuracy
- localStorage limited to ~5MB per browser

---

## [1.0.0] - 2026-04-30

### 🎉 Initial Release

The first stable release of CricManager with complete feature set.

### Added

#### Core Features
- **CSV Upload & Parsing**
  - Supports CricClubs scorecard CSV format
  - Automatic player role classification
  - Deduplication prevents duplicate matches on re-upload
  - Real-time parsing feedback

- **Dashboard**
  - Match overview with KPI metrics
  - Top batsmen and bowlers visualization
  - Match history listing
  - Quick performance snapshot

- **Players Roster**
  - Complete player directory
  - Advanced filtering (role, team, form)
  - Search functionality
  - Detailed statistics per player
  - Catches and run-out tracking

- **Trends & Analytics**
  - Individual player performance tracking
  - Last 5 match history
  - Visual chart analytics
  - Form indicators (hot/stable/cold)
  - Career statistics

- **Partnerships**
  - Batting pair analysis
  - Shared match counter
  - Average combined runs metric
  - Visual performance comparison

- **Team Split**
  - Intelligent player balancing (22/24/26 players)
  - Snake-draft algorithm for fair distribution
  - Role-based composition
  - Strength metrics and balance scoring

- **XI Builder**
  - Flexible squad sizes (11/12/13 players)
  - Smart player ordering
  - Separate batting and bowling order tables
  - Bowling rotation strategy display

- **Match Card**
  - Dual-team XI display
  - Professional card formatting
  - **WhatsApp-ready export** with ASCII tables
  - Print-friendly layouts
  - Match metadata support

#### Technical Features
- **Offline Support**
  - Full localStorage persistence
  - Works completely offline after first load
  - Auto-save on CSV upload
  - Auto-load on browser refresh

- **Data Privacy**
  - All data stays on user's browser
  - No cloud storage or external API calls
  - Zero analytics or tracking
  - Secure by design

- **Responsive Design**
  - Mobile-optimized layouts
  - Works on all device sizes
  - Touch-friendly interface
  - Landscape and portrait support

- **Browser Compatibility**
  - Chrome/Chromium latest
  - Firefox latest
  - Safari latest
  - Edge latest

#### Documentation
- Comprehensive README with feature highlights
- Feature guide with detailed documentation
- Installation guide (3 setup options)
- CSV format documentation with examples
- Contributing guidelines
- This changelog

#### Development
- Single-file HTML architecture (no build process)
- Pure JavaScript (ES6+), HTML5, CSS3
- Chart.js integration via CDN
- Google Fonts for typography
- MIT license

### Technical Details

#### Data Model
- Player object with 25+ statistics fields
- Match object with date, teams, result
- Partnership object with pair metrics
- Database with deduplication tracking

#### Algorithms
- **Player Role Classification**: Based on match participation (batted/bowled)
- **Form Calculation**: Last 5 match trend analysis
- **Team Balancing**: Snake-draft with score weighting
- **Batting Order**: Powerplay avg → Strike rate → Form
- **Bowling Order**: Specialty → Economy → Wickets

#### Statistics
- Batting: Runs, balls, SR, powerplay avg, form
- Bowling: Wickets, overs, economy, specialty, form
- Fielding: Catches, wicket keeper catches, run-outs
- Performance: Last 5 matches, career totals

### File Size & Performance
- HTML file: 66 KB (884 lines)
- Page load: < 1 second
- CSV parsing: 1-2 seconds per match
- localStorage: 2-5 KB per match

### Testing
- ✅ Verified with CricClubs export CSV
- ✅ Tested in Chrome, Firefox, Safari
- ✅ Mobile responsive verified
- ✅ Offline functionality verified
- ✅ All 8 features functional
- ✅ 23 player test data included

### Known Limitations
- Single match per CSV upload (can upload multiple)
- Form calculation needs 4+ matches for accuracy
- Powerplay defined as first 36 balls (~6 overs)
- Death bowling detection uses economy heuristic
- Chart.js requires internet on first load
- localStorage limit ~5MB (sufficient for 100+ matches)

### Contributors
- Prabh Simran Singh (Creator)

### Special Thanks
- Chart.js for visualization library
- Google Fonts for typography
- CricClubs for CSV format inspiration

---

## Version History

### Pre-Release Development
- Multiple feature iterations
- CSV parsing refinements
- UI/UX polishing
- Documentation writing
- Testing and bug fixes
- GitHub setup preparation

---

## Upgrade Guide

### For Version 1.0.0 (First Time Users)
1. Download `index.html` from GitHub
2. Open in any modern browser
3. Upload cricket scorecard CSV
4. Explore features
5. Data automatically saved offline

### Migrating from Previous Builds
If you were using cricket-analyzer-fixed_6.html:
1. Download new `index.html` file
2. Replace old file
3. Your localStorage data is preserved
4. Functionality is identical (with bug fixes)

---

## Semantic Versioning

CricManager follows [Semantic Versioning](https://semver.org/):

- **MAJOR** (X.0.0): Breaking changes
- **MINOR** (0.X.0): New features (backwards compatible)
- **PATCH** (0.0.X): Bug fixes

---

## Release Links

- **GitHub**: [CricManager Repository](https://github.com/prabhsimransingh/CricManager)
- **Live Demo**: [GitHub Pages](https://prabhsimransingh.github.io/CricManager/)
- **Releases**: [GitHub Releases](https://github.com/prabhsimransingh/CricManager/releases)

---

## Contributing

Found a bug or have a feature idea? 

- **Report Issue**: [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues)
- **Submit Code**: See [CONTRIBUTING.md](CONTRIBUTING.md)
- **Ask Questions**: GitHub Issues with "question" label

---

## License

All changes and contributions are under the MIT License. See [LICENSE](../LICENSE) file for details.

---

## FAQ

### Q: When was CricManager released?
A: Version 1.0.0 was released on April 30, 2026.

### Q: How often is CricManager updated?
A: Updates planned as needed based on user feedback and feature requests.

### Q: Can I use older versions?
A: Yes, download from GitHub releases page.

### Q: What's the roadmap?
A: See "Planned Features" in Unreleased section above.

---

## Acknowledgments

Special thanks to:
- Early testers and feedback providers
- CricClubs for CSV format reference
- Open source community for inspiration
- Everyone contributing ideas and improvements

---

*Last Updated: April 30, 2026*

*For more information, see [README.md](../README.md)*
