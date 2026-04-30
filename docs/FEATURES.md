# 🏏 CricManager - Features Guide

Comprehensive documentation for all CricManager features.

---

## 📊 1. Dashboard

**Purpose**: Overview of all matches and top performers

### What You See
- **Match Summary**: Total matches, total players
- **Top Batsmen Chart**: Bar chart of highest run scorers
- **Top Bowlers Chart**: Bar chart of most wicket takers
- **Match History**: List of all uploaded matches with results

### How to Use
1. Upload a CSV file (see Upload tab)
2. Dashboard automatically populates
3. Click on match details to see more info

### Example
```
Match: Clinical vs Surgical (Feb 1st 2026) → Surgical won by 2 wickets
Top Batsman: Ritesh Chhajer (46 runs)
Top Bowler: Vijay Pinni (4 wickets)
Total Players: 23
```

---

## 👥 2. Players Roster

**Purpose**: Complete player directory with detailed statistics

### Features
- **Complete Listing**: All players with comprehensive stats
- **Search**: Find players by name
- **Filter by Role**: Batsman, Bowler, All-Rounder
- **Filter by Team**: Select specific team
- **Filter by Form**: Hot, Stable, Cold
- **Stats Columns**:
  - Runs scored
  - Wickets taken
  - Catches/Run-outs
  - Matches played
  - Strike Rate (for batsmen)
  - Economy (for bowlers)
  - Powerplay Average

### How to Use
1. Go to **Players** tab
2. Use search box to find a player
3. Use role filter to see batsmen, bowlers, or all-rounders
4. Use team filter to isolate one team
5. Use form filter to see hot/cold players

### Player Role Classification
- **Batsman**: Only participated in batting
- **Bowler**: Only participated in bowling
- **All-Rounder**: Both batted and bowled in matches

### Form Indicator
- **🔥 Hot**: Recent 2 matches > previous 2 matches by 15+ runs
- **⚪ Stable**: Average performance trend
- **❄️ Cold**: Recent performance declining

---

## 📈 3. Trends & Analytics

**Purpose**: Individual player performance analysis and form tracking

### Features
- **Player Selection**: Dropdown to select any player
- **Career Statistics**:
  - Total runs (for batsmen)
  - Total wickets (for bowlers)
  - Strike rate / Economy
  - Last 5 match average
  
- **Visual Charts**:
  - Batsman: Bar chart of runs per match
  - Bowler: Line chart of wickets per match
  - All-Rounder: Both batting and bowling charts

- **Last 5 Matches Table**:
  - Date of match
  - Runs scored / Overs bowled
  - Balls faced / Runs given
  - Wickets taken
  - Result (Won/Lost)

### How to Use
1. Go to **Trends** tab
2. Select a player from dropdown
3. View charts and last 5 matches
4. Scroll through match history

### Example
```
Player: Shishir Jain (Clinical - All-Rounder)
Career Stats:
  - Runs: 1
  - Wickets: 1
  - Strike Rate: 16.7%
  - Economy: 3.67

Last 5 Matches: [M1: 1R, 1W]
Form: Stable (needs more matches)
```

### Interpreting Form
- **4+ matches required** for accurate form calculation
- Green (hot) players are in good form
- Blue (cold) players need to rebuild confidence
- Gray (stable) players are consistent

---

## 🤝 4. Partnerships

**Purpose**: Analyze batting partnerships and combination performance

### Features
- **Best Pairs**: Visual bar chart of top batting pairs
- **Partnership Table**: Detailed stats for all partnerships
- **Shared Matches**: Count of matches played together
- **Average Combined Runs**: Average contribution per match

### How to Use
1. Go to **Partnerships** tab
2. View bar chart of top partnerships
3. Scroll table for detailed partnership stats
4. Hover over bars to see exact values

### Requirements
- Partnerships require **minimum 2 shared matches** to appear
- Both players must bat in the same match

### Example
```
Partnership: Ritesh Chhajer + Kumar Sundararaman
Shared Matches: 1
Average Combined Runs: 56 runs per match
```

---

## 🏆 5. Team Split

**Purpose**: Intelligently split players into balanced teams

### Smart Balancing Algorithm
1. **Score Calculation**: Combines runs (40%), wickets (60%), and form bonus
2. **Sorting**: Players sorted by composite score
3. **Distribution**: Snake-draft alternates between teams
4. **Role Balance**: Maintains ~6 batsmen, ~3 bowlers, ~2 all-rounders per team
5. **Strength Metric**: Shows strength difference (lower = more balanced)

### How to Use
1. Go to **Team Split** tab
2. Click **"Select 22"**, **"Select 24"**, or **"Select 26"** button
3. Review selected players
4. Click **"Generate Split"**
5. View balanced Team A vs Team B

### What You Get
- **Team A & Team B**: Side-by-side comparison
- **Player Lists**: All selected players
- **Role Distribution**: Count of batsmen, bowlers, all-rounders
- **Metrics**:
  - Total runs per team
  - Total wickets per team
  - Average strike rate (batsmen)
  - Average economy (bowlers)
- **"Back to Selection"**: Button to try again

### Example Output
```
Team Split (22 players)

TEAM A (11 players)
Roles: 6 Batsmen, 3 Bowlers, 2 All-Rounders
Total Runs: 250 | Total Wickets: 18
Avg SR: 145.2 | Avg Economy: 6.5

vs

TEAM B (11 players)
Roles: 6 Batsmen, 3 Bowlers, 2 All-Rounders
Total Runs: 265 | Total Wickets: 17
Avg SR: 142.8 | Avg Economy: 6.2

⚖️ Balance: Nearly equal strength
```

---

## 🎯 6. XI Builder

**Purpose**: Build optimal playing XI with smart player ordering

### Format Options
- **11 Players** (Standard): 8-9 batsmen + 2-3 bowlers
- **12 Players**: 8-9 batsmen + 3-4 bowlers
- **13 Players**: 9-10 batsmen + 3-4 bowlers

### Smart Ordering
**Batting Order**:
1. Sort by **Powerplay Average** (runs in first 6 overs)
2. Then by **Strike Rate** (highest first)
3. Then by **Form** (hot players first)

**Bowling Order**:
1. Sort by **Specialty** (Powerplay → Middle → Death)
2. Then by **Economy Rate** (lowest first)
3. Then by **Wickets** (most first)

### How to Use
1. Go to **XI Builder** tab
2. Select format: 11, 12, or 13 players
3. Click players to select (max based on format)
4. Click **"🎯 Smart Order"**
5. View optimized batting and bowling orders

### Output
- **Batting Order Table**: Position, name, runs, strike rate, form
- **Bowling Order Table**: Position, name, wickets, economy, specialty
- **Bowling Rotation Strategy**:
  - ⚡ Powerplay bowlers (economy < 4.5, 3+ wickets)
  - 🎯 Middle-over specialists
  - 💀 Death bowlers (35%+ wickets in death overs)

### Example XI
```
XI FORMAT: 11 PLAYERS

BATTING ORDER
1. Ritesh Chhajer (All-Rounder) - SR: 121.0, Hot
2. Rohit Suri (All-Rounder) - SR: 41.7, Stable
3. Parag Vaidya (All-Rounder) - SR: 175.0, Stable
...

BOWLING ORDER
1. Vijay Pinni (All-Rounder) - Economy: 1.67, 4 Wickets
2. Shishir Jain (All-Rounder) - Economy: 3.67, 1 Wicket
...

BOWLING ROTATION STRATEGY
⚡ Powerplay: Vijay Pinni (1.67 econ)
🎯 Middle: Shishir Jain (3.67 econ)
💀 Death: [Available bowlers]
```

---

## 🖨️ 7. Match Card

**Purpose**: Create professional XI cards for both teams and export

### Features
- **Team A XI**: Build and display first team
- **Team B XI**: Build and display second team
- **Team Names**: Customizable names for both teams
- **Match Details**: Date, time, venue
- **Side-by-Side Display**: Both teams shown together
- **WhatsApp Export**: Copy formatted text to clipboard
- **Print Support**: Professional print layout

### How to Use
1. Go to **Match Card** tab
2. Select 11 players for **Team A** from left roster
3. Select 11 players for **Team B** from right roster
4. Fill in match details:
   - Team A Name
   - Team B Name
   - Date
   - Time
   - Venue
5. Click **"📋 Copy for WhatsApp"**
6. Paste into WhatsApp for sharing

### WhatsApp Export Format
```
🏏 TEAM A vs TEAM B 🏆
──────────────────────────────────────────────────
📅 Feb 1, 2026 🕐 2:30 PM 📍 Sports Ground
──────────────────────────────────────────────────

┌─────────────────────┬─────────────────────┐
│ Team A              │ Team B              │
├─────────────────────┼─────────────────────┤
│ 1. Ritesh Chhajer   │ 1. Anubhav Sharma   │
│ 2. Rohit Suri       │ 2. Raviraj M        │
│ 3. Vijay Pinni      │ 3. Kamal Bhatia     │
│ ...                 │ ...                 │
└─────────────────────┴─────────────────────┘

🏏 Cricket Analyzer
```

### Printing
1. Go to **Match Card** tab
2. Click **"🖨 Print"**
3. Save as PDF or print directly
4. Professional layout with both teams

---

## 🔒 8. Offline Support

**Purpose**: Use CricManager without internet after initial load

### How It Works
1. First time: Open CricManager and upload CSV
2. Data saved to **browser localStorage** automatically
3. Next time: Open CricManager without internet
4. All previously uploaded data loads from localStorage

### Data Persistence
- ✅ All player statistics
- ✅ Match history
- ✅ Partnerships
- ✅ Team splits
- ✅ XI builders
- ✅ Match cards

### Limitations (Offline)
- ❌ Chart.js charts won't display (requires CDN)
- ✅ Everything else works perfectly

### Clear Data
To remove all stored data:
1. Go to **Upload** tab
2. Scroll to "Danger Zone"
3. Click **"Clear Database"**
4. Confirm deletion

---

## 🔄 Combining Features

### Workflow Example
```
1. Upload CSV → Dashboard shows match overview
2. Go to Players → Find interesting players
3. Go to Trends → Analyze player form
4. Go to Team Split → Create balanced teams
5. Go to XI Builder → Build optimal 11
6. Go to Match Card → Create professional XI cards
7. Copy WhatsApp text → Share with team
```

---

## ⚙️ Advanced Tips

### Best Practices
- Upload **multiple matches** for better form analysis
- Use **Team Split** for practice match balancing
- Use **XI Builder** for optimized team composition
- **Search filters** to find specific players quickly
- **Print Match Cards** for physical display

### Performance Tips
- Clear database periodically if storing many matches
- Use CSV samples from CricClubs directly
- Refresh page if experiencing slowness
- Use Chrome or Firefox for best performance

### Data Analysis Tips
- Form needs **4+ matches** for accuracy
- Compare batsmen by **Strike Rate** column
- Compare bowlers by **Economy** column
- Use **Partnerships** to identify successful combinations
- Monitor **Trends** to track player improvement

---

## 📱 Mobile Usage

CricManager works on mobile devices:
- **Upload**: Tap CSV file to import
- **View**: All tabs responsive
- **Match Card**: Stacked layout on small screens
- **Print**: Mobile-friendly print styles

---

## 🐛 Feature Troubleshooting

| Issue | Solution |
|-------|----------|
| Players showing wrong role | Clear DB + hard refresh + re-upload CSV |
| Trends dropdown empty | Upload CSV successfully first |
| Charts not showing | Check internet (Chart.js from CDN) |
| Team Split shows fewer players | Ensure minimum 22 players selected |
| Data disappears after refresh | Enable localStorage in browser |
| CSV upload fails | Verify CricClubs format (see CSV_FORMAT.md) |

---

*For detailed technical documentation, see the main [README.md](../README.md)*
