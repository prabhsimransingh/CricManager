# 📊 CSV Format Documentation

Complete guide to preparing cricket scorecard CSVs for CricManager

---

## Overview

CricManager parses **CricClubs scorecard export format** CSV files.

### Quick Facts
- ✅ Format: CricClubs scorecard export
- ✅ Structure: 4 sections (2 batting, 2 bowling)
- ✅ Encoding: UTF-8 recommended
- ✅ Dialect: Standard CSV (comma-separated)
- ✅ Size: ~2-5 KB per match

---

## Expected CSV Structure

A typical CricManager-compatible CSV has this structure:

```
[Header Line with Date and Match Info]
[Team Names Line]
[Blank Line]

,,,Team1 Batting
[Column Headers]
[Player data rows...]
[Totals/Summary line]

,,,Team2 Bowling
[Column Headers]
[Player data rows...]
[Totals/Summary line]

,,,Team2 Batting
[Column Headers]
[Player data rows...]
[Totals/Summary line]

,,,Team1 Bowling
[Column Headers]
[Player data rows...]
[Totals/Summary line]
```

---

## Detailed Section Structure

### Header Line
Extracts date and match result (if available):

```
Feb 1st 2026:  LeagueSurgical won by 2 Wickets (02/01/2026)
```

- Detects date format: "Month Day Year" (e.g., "Feb 1st 2026")
- Extracts winner: "Team won by X Wickets/Runs"
- Format is flexible (case-insensitive)

### Team Names Line
Format:
```
                     Team1 Vs Team2
```

- Uses pattern: `Team1` **vs** `Team2` (case-insensitive)
- Required for player assignment
- Can have extra spaces/tabs

---

## Section Headers

All section headers follow this pattern:

```
,,,TeamName Batting
```

or

```
,,,TeamName Bowling
```

### Rules
- Prefix: 3 or more commas (`,,,`)
- Team name: Any text without commas
- Keywords: "Batting" or "Bowling" (case-insensitive)
- Can have whitespace

### Examples
```
,,,Clinical Batting        ✅ Valid
,,,Surgical Bowling        ✅ Valid
,,,Team1 Batting           ✅ Valid
,,,Team 2 BOWLING          ✅ Valid (case-insensitive)
,,,My Team's Batting       ❌ Invalid (apostrophe issues)
```

---

## Batting Section Format

### Column Headers
```
BatsMan, How Out, Fielder, Bowler, Runs, Balls, Fours, Sixers
```

**Column Order** (index 0-7):
| Index | Header | Type | Required | Example |
|-------|--------|------|----------|---------|
| 0 | BatsMan | String | ✅ Yes | Shishir Jain |
| 1 | How Out | String | ❌ No | ct, b, lbw, ro, ctw |
| 2 | Fielder | String | ❌ No | Ravi K, Anubhav S |
| 3 | Bowler | String | ❌ No | Puneet P, Subbu K |
| 4 | Runs | Integer | ✅ Yes | 1, 25, 46 |
| 5 | Balls | Integer | ✅ Yes | 6, 30, 38 |
| 6 | Fours | Integer | ✅ Yes | 0, 2, 6 |
| 7 | Sixers | Integer | ✅ Yes | 0, 1, 1 |

### Sample Batting Data
```
Shishir Jain,ctw,Ravi K,Anubhav S,1,6,0,0
Vinod Baya,,,,4,15,0,0
Venkat Visvanathan,b,,Anubhav S,0,2,0,0
Deven Samant,ct,Anubhav S,Raviraj M,12,8,1,1
Ritesh Chhajer,,,,46,38,6,1
```

### Dismissal Types
```
ct    = Caught
ctw   = Caught by wicket keeper
b     = Bowled
lbw   = LBW (Leg Before Wicket)
ro    = Run Out
rt    = Retired
(empty) = Not Out
```

### Powerplay Detection
- **First 6 overs** ≈ first 36 balls
- Runs scored in first 36 balls tracked separately
- Used for "Powerplay Average" stat

---

## Bowling Section Format

### Column Headers
```
Bowler, Overs, Maidens, Runs, Wickets, Wides, No Balls, Hattricks, Dot Balls
```

**Column Order** (index 0-8):
| Index | Header | Type | Required | Example |
|-------|--------|------|----------|---------|
| 0 | Bowler | String | ✅ Yes | Shishir Jain |
| 1 | Overs | Float | ✅ Yes | 3.0, 4.2, 2.5 |
| 2 | Maidens | Integer | ✅ Yes | 0, 1, 2 |
| 3 | Runs | Integer | ✅ Yes | 11, 28, 15 |
| 4 | Wickets | Integer | ✅ Yes | 1, 2, 0 |
| 5 | Wides | Integer | ❌ No | 1, 0, 2 |
| 6 | No Balls | Integer | ❌ No | 0, 1, 1 |
| 7 | Hattricks | Integer | ❌ No | 0 (rarely used) |
| 8 | Dot Balls | Integer | ❌ No | 10, 15, 8 |

### Sample Bowling Data
```
Anubhav Sharma,3.0,0,16,2,3,1,0,13
Puneet Prabh Friend,3.0,1,5,1,0,0,0,15
Raviraj Murdeshwar,3.0,0,16,3,0,0,0,11
Shishir Jain,3.0,0,11,1,1,0,0,10
```

### Overs Format
- Format: `O.B` where O = overs, B = balls
- Examples:
  - `3.0` = 3 overs, 0 balls (18 balls total)
  - `3.2` = 3 overs, 2 balls (20 balls total)
  - `4.5` = 4 overs, 5 balls (29 balls total)

### Economy Calculation
```
Economy Rate = Runs Given ÷ Overs Bowled
Example: 11 runs in 3.0 overs = 3.67 economy
```

### Death Bowling Detection
- **Heuristic**: Economy > 8 in 3+ overs
- Identifies bowlers handling death overs
- Used for "Bowling Speciality" (Death)

---

## Section Order

**Critical**: Sections must follow this order:

1. **Team1 Batting** - First team's batting stats
2. **Team2 Bowling** - Second team's bowling stats
3. **Team2 Batting** - Second team's batting stats
4. **Team1 Bowling** - First team's bowling stats

### Example
```
Clinical Batting    → First (Team1)
Surgical Bowling    → Second (Team2)
Surgical Batting    → Second (Team2)
Clinical Bowling    → First (Team1)
```

---

## Special Rows to Skip

### These rows are automatically ignored:

1. **Header rows**
   ```
   BatsMan, How Out, Fielder, ...
   Bowler, Overs, Maidens, ...
   ```

2. **Summary rows**
   ```
   Byes: 5, Leg Byes: 0, Wickets: 9, Wides: 7, ...
   Total, 22.0, 1, 127, 9, 7, 5, 0, 81
   ```

3. **Fall of Wickets sections**
   ```
   Fall of Wickets
   Shishir, 1-3, Over 0.6
   ```

4. **Extras/Total rows**
   ```
   Extras, 5, 0, 7, 0
   Total Runs, 132, 22.0
   ```

5. **Empty lines**
   ```
   (completely blank or whitespace-only)
   ```

---

## Data Validation Rules

### Player Names
- ✅ Must be 2+ characters
- ✅ Can contain spaces: "Shishir Jain"
- ✅ Can contain abbreviations: "Raviraj M"
- ❌ Cannot be "Fall of Wickets" or similar keywords

### Numbers
- Runs: Integer ≥ 0
- Balls/Overs: Integer or float ≥ 0
- Wickets: Integer 0-5 (typical range)
- Fours/Sixes: Integer ≥ 0

### Minimum Columns
- **Batting**: At least 8 columns
- **Bowling**: At least 5 columns

---

## Complete Example CSV

Here's a minimal complete example:

```csv
Feb 1st 2026:  Surgical won by 2 Wickets
Clinical Vs Surgical



,,,Clinical Batting

	BatsMan, How Out, Fielder, Bowler, Runs, Balls, Fours,Sixers
	Shishir Jain,ctw,Ravi K,Anubhav S,1,6,0,0
	Ritesh Chhajer,,,,46,38,6,1
	Kumar Sundararaman,ct,Anubhav S,Puneet P,10,19,0,0

	Byes: 5 , Leg Byes: 0, Wickets : 9

,,,Surgical Bowling 

	Bowler,Overs,Maidens,Runs,Wickets,Wides,No Balls,Hattricks,Dot Balls
	Anubhav Sharma,3.0,0,16,2,3,1,0,13
	Puneet Prabh Friend,3.0,1,5,1,0,0,0,15
	Raviraj Murdeshwar,3.0,0,16,3,0,0,0,11

	Total, 22.0 ,1,127,9,7,5,0,81

,,,Surgical Batting

	BatsMan, How Out, Fielder, Bowler, Runs, Balls, Fours, Sixers
	Ravi Poruri,ro,Shishir Jain,Kamal B,15,20,1,0
	Kamal Bhatia,ct,Ritesh Chhajer,Prabh Singh,5,8,0,0

,,,Clinical Bowling

	Bowler,Overs,Maidens,Runs,Wickets,Wides,No Balls,Hattricks,Dot Balls
	Shishir Jain,3.0,0,11,1,1,0,0,10
	Vijay Pinni,3.0,1,5,4,1,1,0,15
```

---

## Getting CSV from CricClubs

### Export Steps

1. **Go to CricClubs website**: https://www.cricclubs.com/
2. **Find your match**
3. **Click "Export"** or **"Download Scorecard"**
4. **Select "Excel CSV"** format
5. **Save file** to your computer
6. **Open in CricManager**

### File Naming
- Recommended: `match-date-teams.csv`
- Examples:
  - `2026-02-01-clinical-vs-surgical.csv`
  - `friendly-match-teams.csv`

---

## Common Issues & Solutions

### Issue: "Teams not found"

**Cause**: Team names line missing or malformed

**Solution**:
```
❌ Wrong:
Team1 Vs Team2

✅ Right:
                     Team1 Vs Team2
```

### Issue: "Parsing failed on line X"

**Cause**: Invalid data format

**Solution**:
1. Check column count (8 for batting, 5+ for bowling)
2. Verify number format (no letters in Runs, Balls, etc.)
3. Check for extra commas or special characters

### Issue: Some players missing

**Cause**: Player name containing special characters

**Solution**:
- Remove apostrophes: "O'Brien" → "O Brien"
- Keep simple names: "Shishir Jain" (OK)

### Issue: Wickets showing as 0

**Cause**: Bowler with 0 wickets in match

**Solution**: This is normal! Not all bowlers take wickets.
- Shows as "Bowler" role if they bowled
- Data is correct

---

## CSV Format Validation Checklist

- [ ] File is CSV format (comma-separated)
- [ ] UTF-8 encoding (default)
- [ ] Has all 4 sections in correct order
- [ ] Team names match between batting and bowling
- [ ] All columns present (even if empty)
- [ ] Numbers are valid (no letters in numeric columns)
- [ ] Player names are 2+ characters
- [ ] No duplicate player names in same team
- [ ] Overs format is correct (O.B notation)
- [ ] Downloaded from CricClubs or similar format

---

## Sample CSV

Download sample: [viewScorecardExcel.csv](../samples/viewScorecardExcel.csv)

This file is included in the repository and can be used for testing.

---

## FAQ

**Q: Can I use CSVs from other cricket platforms?**
A: Only if they follow the CricClubs format (4 sections, same column structure)

**Q: What if my CSV format is slightly different?**
A: CricManager is flexible with spacing/formatting, but requires the basic structure

**Q: Can I manually create a CSV?**
A: Yes! Follow the format above and save as `.csv`

**Q: Why does the parser skip certain rows?**
A: To avoid counting headers, totals, and "Fall of Wickets" multiple times

**Q: What's the maximum file size?**
A: ~50 KB per match (very large files), ~2-5 KB typical

---

## Support

- **CSV Issues?** Check [INSTALLATION.md](INSTALLATION.md#csv-upload-fails)
- **Format Questions?** See examples above
- **Report Bug?** [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues)

---

*Last Updated: April 2026*
