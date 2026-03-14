# WeightWise — Setup Guide

## What's included
```
index.html      ← The entire app (one file)
manifest.json   ← Makes it installable as a phone app
sw.js           ← Service worker for offline use
README.md       ← This guide
```

---

## Step 1: Deploy to GitHub Pages (5 minutes)

1. Go to [github.com](https://github.com) and sign in (or create a free account)
2. Click **New Repository** → name it `weightwise` → set to **Public** → click **Create**
3. Upload all 4 files (`index.html`, `manifest.json`, `sw.js`, `README.md`)
4. Go to **Settings → Pages** → Source: **Deploy from branch** → Branch: `main` → `/root` → **Save**
5. Your app is live at: `https://YOUR-USERNAME.github.io/weightwise/`

---

## Step 2: Install on Your Phone

### iPhone (Safari only)
1. Open your GitHub Pages URL in **Safari**
2. Tap the **Share** button (rectangle with arrow)
3. Scroll down → **Add to Home Screen**
4. Tap **Add** — WeightWise icon appears on your home screen!

### Android (Chrome)
1. Open your GitHub Pages URL in **Chrome**
2. Tap the **⋮** menu → **Install App** or **Add to Home Screen**
3. Tap **Install** — done!

---

## Step 3: Set Up Google Sheets Database (optional but recommended)

This lets your data sync across all devices (phone, laptop, tablet).

### A. Create the Google Sheet
1. Go to [sheets.google.com](https://sheets.google.com) → create a new blank spreadsheet
2. Name it **WeightWise Data**

### B. Add the Apps Script
1. In your spreadsheet: **Extensions → Apps Script**
2. Delete any existing code
3. In the WeightWise app → **Settings → Copy Apps Script Code**
4. Paste it into the Apps Script editor
5. Click **Save** (💾 icon)

### C. Deploy as Web App
1. Click **Deploy → New Deployment**
2. Click the gear ⚙ next to "Type" → select **Web app**
3. Settings:
   - Description: `WeightWise API`
   - Execute as: **Me**
   - Who has access: **Anyone**
4. Click **Deploy**
5. Click **Authorize access** → choose your Google account → Allow
6. **Copy the Web App URL** (looks like `https://script.google.com/macros/s/ABC.../exec`)

### D. Connect in WeightWise
1. Open WeightWise → **Settings** (⚙ icon)
2. Paste the URL into **Google Apps Script Web App URL**
3. Tap **Test Connection** → should say "✓ Connected!"
4. Tap **Save Settings**

Now every weight log automatically saves to your Google Sheet! You can also open the sheet directly to see/edit your data.

---

## Features

| Feature | Description |
|---------|-------------|
| 📊 **Dashboard** | Current weight, goal progress bar, this week's chart, streak |
| ➕ **Log** | Quick weight entry with date, unit (kg/lbs), and optional note |
| 📈 **Insights** | Trend chart, avg loss/week, ETA to goal, BMI, pace rating, monthly breakdown |
| 📋 **History** | All entries with delta indicators, delete option |
| ☁️ **Google Sheets sync** | Persist data across all devices |
| 🔥 **Streaks** | Current and best logging streaks |
| 📱 **PWA** | Installable, works offline |
| 🌙 **Dark mode** | Always beautiful |

---

## Data & Privacy

- All data stored locally in your browser (`localStorage`) by default
- Google Sheets connection is **your own** Google account — no third parties
- No tracking, no ads, no accounts needed
- Export anytime via **Settings → Export CSV**

---

## Customisation

Everything is in `index.html`. Easy things to change:
- Colors: Edit the `:root` CSS variables at the top
- Default unit: Change `unit: 'kg'` to `unit: 'lbs'`
- App name: Find `WeightWise` in the HTML

---

*Built with ❤️ — one HTML file, no frameworks, no dependencies except Chart.js*
