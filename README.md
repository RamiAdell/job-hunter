# 🎯 Job Hunter

**A single HTML file that turns your job search into a system.**

No backend. No sign-up. No subscriptions. Just drop it in your browser and start hunting.

---

## What is this?

Job Hunter generates LinkedIn job search URLs for every combination of role and country you care about — and opens them all in one click. It's built for people who are actively searching and tired of manually setting the same filters over and over.

You have 5 job titles keywords and 7 countries you're targeting? That's 35 LinkedIn searches. Job Hunter does all 35 in a few seconds, fully filtered to your preferences.

---

## Features

### 🔑 Keyword & Category System
Organize your target roles into categories that make sense for you — `Backend`, `Frontend`, `Data`, `DevOps`, or whatever you come up with. Every keyword gets a color-coded badge so you can scan at a glance.

### 🌍 Multi-Country Search
Add any country by name, emoji flag, and LinkedIn GeoId. The tool ships with a built-in GeoId reference so you don't have to dig around. Mark one as your "local" country to spot it easily in the results.

### ⏱ Smart Filters
- **Time Range** — Any Time, Today, 3 Days, This Week, This Month, or a custom value (e.g. "last 6 hours")
- **Work Type** — Remote, Hybrid, On-site (multi-select)
- **Easy Apply** — filter to jobs you can apply for without leaving LinkedIn
- **Visa Mode** — appends "visa sponsorship" to every search query automatically
- **Tab Speed** — throttle how fast new tabs open so your browser doesn't panic

### 📋 Bulk Actions
- Open all visible searches at once, or just a selected subset
- Download a `.bat` file if your browser blocks popups — it opens every URL through the terminal instead
- Select All / Clear / individual card selection

### 💾 Persistence That Makes Sense
Everything saves to `localStorage` automatically as you type. Hit **Save to File** and it bakes your full setup (countries, keywords, settings) permanently into a new HTML file you can carry anywhere — email to yourself, put on a USB drive, share with a friend.

---

## Getting Started

### 1 — Download the file
Grab `job_hunter.html` from this repo.

### 2 — Open it in your browser
Double-click it. No server, no `npm install`, no nothing.

### 3 — Add your countries

Click **🌍 Manage Countries** in the filter panel. For each country you want to search in, you need:
- A flag emoji (e.g. `🇩🇪`)
- The country name
- Its LinkedIn GeoId

**Finding a GeoId:** Go to `linkedin.com/jobs/search/`, click the Location filter and type the country name, then look at the URL — you'll see `geoId=XXXXXXX`. Copy that number.

Common ones are already listed in the modal for reference (US, UK, DE, FR, NL, CA, AU, SG, JP, SA, AE, ES, PL, PT, EG).

![alt text](/image.png)

### 4 — Add keyword categories

In the **Keywords** panel, scroll to *Keyword Categories*. Type a category name like `Backend` or `Data Science` and click **+ Add Type**. Add as many as you need.

![alt text](Screenshots/image-1.png)

### 5 — Add your keywords

Type a job title in the keyword input, select its category from the dropdown, and click **+ Add Keyword**. These are the search terms that get combined with every country.

Examples: `Senior React Developer`, `Data Analyst`, `DevOps Engineer`, `Product Manager`

![alt text](Screenshots/image-2.png)

### 6 — Set your filters and open

Pick a time range, choose remote/hybrid/on-site, toggle Easy Apply if you want it — then hit **Open All ↗** or select specific cards and click **Open Selected**.

![alt text](Screenshots/image-3.png)

---

## Allowing Popups

When you open many tabs at once, browsers block them by default. Here's how to fix it:

### Chrome / Edge
1. Look for a popup blocked icon (🔒 or a small icon) in the right side of the address bar
2. Click it → select **"Always allow popups from this site"**
3. Click **Open All** again

![alt text](Screenshots/image-4.png)

### Firefox
1. A yellow bar appears at the top of the page — click **Options** → **Allow popups for this page**

### Safari
1. Go to **Safari → Settings → Websites → Pop-up Windows**
2. Find the page and set it to **Allow**

### If popups are a pain: use the .bat file
Click **📥 .bat (All)** in the action bar. It downloads a Windows batch script that opens every URL one by one through your default browser — no popup permissions needed.

---

## Saving Your Setup

Your data saves to `localStorage` automatically, but that's tied to your browser. To make it truly portable:

1. Click **Save to File** in the action bar
2. A new `.html` file downloads with all your countries, keywords, and settings baked in
3. Open that file anywhere — different browser, different computer, send it to a friend

---

## Tips & Tricks

**Visa Mode** adds `"visa sponsorship"` to every search query. Useful if you need sponsorship and want to pre-filter results. Toggle it in the Extras section.

**Filter by Country or Type** — use the pills in the filter panel to narrow down what's visible without deleting anything. Useful when you want to focus on one region at a time.

**Custom time ranges** — the preset pills go up to "This Month", but you can type any number in the custom field. `6 hours`, `2 days`, `3 weeks` — all work.

**Tab Speed slider** — if LinkedIn is flagging you or tabs aren't loading fully, slow it down. 800–1200ms is a safe range. 200ms is fast but your browser will sweat.

**Editable title** — click the "Job Hunter" title or subtitle in the header to rename them. Useful if you're making separate files for different search campaigns (e.g. "Europe Fintech Hunt 2025").

---

## How URLs are built

Every card generates a LinkedIn job search URL like this:

```
https://www.linkedin.com/jobs/search/?
  keywords=Senior+React+Developer+visa+sponsorship
  &geoId=101282230
  &distance=25
  &f_TPR=r604800
  &f_LF=f_AL
  &f_WT=2,3
```

Parameters used:
| Param | What it does |
|---|---|
| `keywords` | Your keyword (+ "visa sponsorship" if Visa Mode is on) |
| `geoId` | The country's LinkedIn geographic ID |
| `distance` | Search radius in miles (fixed at 25) |
| `f_TPR` | Time posted range (e.g. `r604800` = last 7 days) |
| `f_LF` | `f_AL` = Easy Apply only |
| `f_WT` | Work type: `1`=On-site, `2`=Remote, `3`=Hybrid |

---

## File structure

It's one file. Everything — HTML, CSS, JavaScript, your saved data — lives in `job_hunter.html`. That's intentional. No build tools, no dependencies, no node_modules folder. Open and use.

---

## Browser support

Works in any modern browser: Chrome, Firefox, Edge, Safari, Arc. The `.bat` file is Windows-only (for popup-blocked environments).

---

## Contributing

Feel free to open issues or PRs. Common areas for improvement:
- Support for more job platforms (Indeed, Glassdoor, etc.)
- Drag-to-reorder countries and keywords
- Export/import as JSON
- Dark mode

---

## License

MIT. Do whatever you want with it.

---

*Shared to help serious job seekers. May Allah open the best doors for all of us.*
