# 📥 Installation & Setup Guide

Three ways to use CricManager - pick the one that works for you!

---

## Option 1: Online (GitHub Pages) - Easiest ⭐

**No installation required!**

👉 **Open in browser**: [CricManager Live Demo](https://prabhsimransingh.github.io/CricManager/)

### Pros
- ✅ No download needed
- ✅ Always latest version
- ✅ Works on all devices
- ✅ No installation headaches

### Cons
- ❌ Requires internet connection
- ❌ Can't host your own version

---

## Option 2: Local File (Offline) - Recommended

**Download and run locally on your computer**

### Requirements
- Modern web browser (Chrome, Firefox, Safari, or Edge)
- Internet connection **only for first load** (to download Chart.js)
- ~100 KB free disk space

### Steps

#### Windows

1. **Download the file**
   - Go to [GitHub Releases](https://github.com/prabhsimransingh/CricManager/releases)
   - Download `index.html`
   - Save to a folder (e.g., `C:\Users\YourName\Downloads`)

2. **Open in browser**
   - Double-click `index.html`
   - Or right-click → "Open with" → Your browser

3. **First use**
   - Ensure internet is on (to load Chart.js from CDN)
   - Upload your CSV file
   - Close the browser if desired; data is saved

4. **Next time**
   - Open `index.html` again (no internet required)
   - All previous data loads from localStorage

#### macOS

1. **Download the file**
   - Go to [GitHub Releases](https://github.com/prabhsimransingh/CricManager/releases)
   - Download `index.html`
   - Save to a folder (e.g., `~/Downloads`)

2. **Open in browser**
   - Double-click `index.html`
   - Or open Safari/Chrome and drag `index.html` onto the browser window

3. **First use**
   - Ensure internet is on
   - Upload CSV file
   - Done!

4. **Next time**
   - Double-click `index.html` (works offline)

#### Linux

1. **Download the file**
   ```bash
   curl -o index.html https://raw.githubusercontent.com/prabhsimransingh/CricManager/main/index.html
   ```

2. **Open in browser**
   ```bash
   # Chrome
   google-chrome index.html
   
   # Firefox
   firefox index.html
   
   # Or any browser
   xdg-open index.html
   ```

3. **First use**
   - Ensure internet connection
   - Upload CSV
   - Works offline from then on

### Pros
- ✅ Works offline after first load
- ✅ No internet required later
- ✅ Fast loading
- ✅ Full data privacy (stays on your computer)
- ✅ Can use on airplane mode

### Cons
- ❌ Need to download file manually
- ❌ Chart.js requires CDN on first load

---

## Option 3: From Source (Development)

**Clone the repository and run locally**

### Requirements
- Git installed
- Text editor or IDE (VS Code recommended)
- Python 3.x (for local web server)
- Modern web browser

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/prabhsimransingh/CricManager.git
   cd CricManager
   ```

2. **Start a local web server**
   
   **Python 3:**
   ```bash
   python -m http.server 8000
   ```
   
   **Python 2:**
   ```bash
   python -m SimpleHTTPServer 8000
   ```
   
   **Node.js (if installed):**
   ```bash
   npx http-server
   ```

3. **Open in browser**
   ```
   http://localhost:8000/
   ```

4. **Start using**
   - Upload your CSV file
   - All features work

### For Development
- Edit `index.html` to customize
- Refresh browser to see changes (Ctrl+Shift+R for hard refresh)
- All changes are live

### Pros
- ✅ Full control of source code
- ✅ Can modify and customize
- ✅ Can contribute improvements
- ✅ Learn from the code

### Cons
- ❌ More setup required
- ❌ Need to run web server

---

## 🌐 Browser Setup

### Supported Browsers

| Browser | Version | Setup |
|---------|---------|-------|
| Chrome/Chromium | Latest | Just open HTML |
| Firefox | Latest | Just open HTML |
| Safari | Latest | Just open HTML |
| Edge | Latest | Just open HTML |
| Opera | Latest | Just open HTML |
| Internet Explorer | 11 | ❌ **Not supported** |

### Browser Configuration

#### Enable localStorage (usually default)
1. Open browser DevTools (F12)
2. Go to **Application** or **Storage** tab
3. Check **localStorage** section
4. If empty, storage might be disabled
5. Most browsers have it enabled by default

#### Disable Pop-up Warnings
- Some browsers warn about opening local HTML files
- This is normal and safe
- Click "Continue" or "Proceed"

---

## 🔐 Privacy & Security

### Your Data is Safe
✅ **All data stays on your computer**
- No cloud upload
- No external servers
- No analytics or tracking
- No third-party access

### Only External Connection
- Chart.js library (from `cdnjs.cloudflare.com`)
- Only used for charts
- No personal data sent
- Can work offline without charts

### Verification
Check network requests in DevTools:
1. Open DevTools (F12)
2. Go to **Network** tab
3. Only see `cdnjs.cloudflare.com` for Chart.js
4. No data sent to any other server

---

## 💾 Data Storage

### Where is Data Stored?
**Browser localStorage** on your computer:
- Windows: `AppData\Local\[Browser]\User Data\Local Storage`
- macOS: `~/Library/Application Support/[Browser]/`
- Linux: `~/.config/[Browser]/`

### Accessing Your Data
In browser DevTools:
```javascript
// View all data
console.log(localStorage)

// View CricManager data
console.log(JSON.parse(localStorage.getItem('cricket-db')))

// Backup data
copy(JSON.stringify(localStorage))
```

### Clear Data
1. Browser Settings → Clear browsing data
2. Select "Cookies and cached images/files"
3. Select date range
4. Click "Clear"

Or use in-app button:
1. Go to **Upload** tab
2. Scroll to "Danger Zone"
3. Click "Clear Database"

---

## 🚀 First Launch Checklist

- [ ] Downloaded or opened CricManager
- [ ] Browser opened successfully
- [ ] Prepared your CSV file (CricClubs format)
- [ ] Clicked "Upload" tab
- [ ] Selected CSV file
- [ ] Clicked "Upload & Parse"
- [ ] Verified match loaded successfully
- [ ] Explored different tabs
- [ ] All features working

---

## 🐛 Troubleshooting

### Problem: "Chrome can't access file"

**Solution**: Open via local web server (Option 3)

```bash
python -m http.server 8000
# Then open http://localhost:8000/
```

### Problem: CSV Upload Fails

**Solution**: Verify CSV format
1. Check [CSV_FORMAT.md](CSV_FORMAT.md)
2. Use sample CSV from CricClubs directly
3. Check browser console (F12) for errors
4. Try different browser

### Problem: Charts Not Showing

**Solution**: Check internet connection
1. Charts require Chart.js from CDN
2. Ensure internet is on
3. Check DevTools Network tab
4. Clear browser cache (Ctrl+Shift+Delete)
5. Refresh page

### Problem: Data Lost After Refresh

**Solution**: Enable localStorage
1. Check browser's privacy settings
2. Enable "Allow local storage"
3. Try different browser
4. Try incognito/private window
5. Clear site data and retry

### Problem: "Trends dropdown is empty"

**Solution**: Upload CSV first
1. Go to Upload tab
2. Upload CSV successfully
3. Return to Trends
4. Dropdown should now populate

### Problem: Slow Performance

**Solution**: Clear old data
1. Upload tab → "Clear Database"
2. Re-upload CSV
3. Or close/reopen browser
4. Try different browser
5. Check system RAM usage

---

## 📱 Mobile Setup

### iPhone/iPad (Safari)

1. **Open Safari browser**
2. **Visit**: https://prabhsimransingh.github.io/CricManager/
3. **First time**: Ensure WiFi is on (Chart.js download)
4. **Upload CSV**: Tap "Choose File"
5. **Works offline**: After first load, works without WiFi

### Android (Chrome/Firefox)

1. **Open Chrome or Firefox**
2. **Visit**: https://prabhsimransingh.github.io/CricManager/
3. **First time**: Ensure WiFi/data is on
4. **Upload CSV**: Tap "Choose File"
5. **Select CSV**: From device storage or cloud
6. **Works offline**: After first load

### Limitations on Mobile
- ✅ All features work
- ✅ Responsive design
- ✅ Touch-friendly
- ✅ Print support
- ❌ Slightly smaller screens (landscape recommended)

### Tips
- **Landscape mode** works better
- **Fullscreen mode** available on some browsers
- **Add to home screen** for quick access:
  - iOS: Share → Add to Home Screen
  - Android: Menu → Install app

---

## 🔄 Updating CricManager

### Online Version (GitHub Pages)
- **Automatic**: Always on latest version
- No action needed

### Local File (Downloaded)
1. **Check for updates**: Visit [GitHub Releases](https://github.com/prabhsimransingh/CricManager/releases)
2. **Download new version**: Get latest `index.html`
3. **Replace old file**: Overwrite previous `index.html`
4. **Data is safe**: Your localStorage data won't be affected

### From Source (Cloned)
```bash
cd CricManager
git pull origin main
```

---

## 📚 Next Steps

1. **Read**: [FEATURES.md](FEATURES.md) - All feature documentation
2. **Learn**: [CSV_FORMAT.md](CSV_FORMAT.md) - CSV requirements
3. **Contribute**: [CONTRIBUTING.md](CONTRIBUTING.md) - How to help
4. **Report Issues**: [GitHub Issues](https://github.com/prabhsimransingh/CricManager/issues)

---

## ✅ Installation Complete!

You're all set! Now:
1. Upload your cricket scorecard CSV
2. Explore the features
3. Build your XI
4. Share match cards on WhatsApp

**Need help?** Check the [README.md](../README.md) or [FEATURES.md](FEATURES.md)

---

*Last Updated: April 2026*
