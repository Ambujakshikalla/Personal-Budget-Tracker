# 💸 SpendWise — Personal Expense Tracker

A fully client-side personal finance tracker. No server, no account, no database — everything runs in your browser.

## ✨ Features

| Feature | Details |
|---|---|
| Add Expenses | Manual entry with amount, category, date, notes |
| Auto-Categorize | Keyword matching (Amazon, HEB, Geico, etc.) |
| Monthly Dashboard | Total spend, pie + bar charts, top category |
| Budget Tracking | Set per-category limits with progress bars + alerts |
| Insights | 6-month trend, recurring expense detection |
| Export | JSON + CSV export; JSON import |
| Offline-first | 100% browser localStorage — no internet needed after load |

## 🗂️ Categories

Groceries · Shopping · Medical · Car + Insurance + Gas · Rent · Health Insurance · Food · Travel · Amazon · Money Transfer to India · Visas · Phone · Misc · Investments + Savings

---

## 🚀 How to Run

### Option 1 — Open directly (simplest)
1. Download `index.html`
2. Double-click to open in Chrome, Firefox, or Edge
3. Done — no installation needed!

### Option 2 — Local dev server (recommended for development)
```bash
# Python (comes pre-installed on Mac/Linux)
python3 -m http.server 8080
# Then open: http://localhost:8080

# OR with Node.js (npx)
npx serve .
```

### Option 3 — GitHub Pages (free hosting)
```bash
# 1. Create a new repo on GitHub
git init
git add .
git commit -m "Initial commit: SpendWise expense tracker"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/spendwise.git
git push -u origin main

# 2. Go to: GitHub repo → Settings → Pages
# 3. Source: Deploy from branch → main → / (root)
# 4. Your app will be live at: https://YOUR_USERNAME.github.io/spendwise/
```

### Option 4 — Netlify Drop (instant, no signup needed)
1. Go to [netlify.com/drop](https://app.netlify.com/drop)
2. Drag and drop the `index.html` file
3. Get a live URL instantly

---

## 📁 Project Structure

```
spendwise/
├── index.html      ← Everything (HTML + CSS + JS in one file)
└── README.md       ← This file
```

Single-file design means zero build steps, zero dependencies to install, works anywhere.

---

## 🔧 Customization

### Add a new category
In `index.html`, find the `CATEGORIES` array and add your category:
```js
const CATEGORIES = [
  'Groceries', 'Shopping', /* ... */ 'Your New Category'
];
```
Then add a color in `CAT_COLORS` at the matching index.

### Add a new auto-categorize keyword
In the app: **Add Expense → Auto-Categorize Keywords → Add keyword**

Or directly in code, find `DEFAULT_KEYWORDS`:
```js
const DEFAULT_KEYWORDS = {
  'amazon': 'Amazon',
  'your keyword': 'Your Category',
  // ...
};
```

### Change default budgets
Find `DEFAULT_BUDGETS` and update the values:
```js
const DEFAULT_BUDGETS = {
  'Rent': 2000,       // change to your rent
  'Groceries': 600,   // change to your grocery budget
  // ...
};
```

---

## 💾 Data Storage

All data is stored in **browser localStorage** under these keys:
- `sw_expenses` — array of expense objects
- `sw_budgets` — object of category → monthly limit
- `sw_keywords` — object of keyword → category

To back up your data: **Settings → Export Data as JSON**
To restore: **Settings → Import JSON Data**

---

## 🖥️ Browser Support

| Browser | Support |
|---|---|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full |
| Safari | ✅ Full |
| Mobile browsers | ✅ Responsive |

---

## 📌 Tips

- **Load sample data first**: Settings → Load Sample Data — to see the app in action
- **Recurring detection**: Works best after 2–3 months of data
- **Budget alerts**: Triggered at 80% and 100% of each category's budget
- **CSV export**: Open in Excel or Google Sheets for further analysis

---

## 📄 License

MIT — free to use, modify, and distribute.
