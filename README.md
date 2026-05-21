# Pipe RM Calculator

A completely self-contained, client-side web application designed to calculate raw pipe sizes and weights for order planners. The calculator supports custom rules, series-based stock mapping, and Excel import/export to streamline order processing.

---

## 🚀 Features

### 1. Pipe Database & Calculator
- Searchable database of 1,000+ pipes (including `KM`, `H`, `AH`, `HM` series).
- Instant calculations of raw dimensions, weight in meters, and total order weight.
- Custom product builder to dynamically construct and calculate pipes not present in the standard database.

### 2. Series-Based Stock Rules & Validation
- **Range-Based Rules:** Target specific Finish OD ranges (e.g., `From OD` to `To OD`).
- **Series-Based Rules:** Target specific pipe name prefixes (e.g., `'KM'`, `'H'`, `'AH'`).
- **Real-Time Validation:**
  - Blocks adding rules if `OD Allowance` is less than `ID Allowance`.
  - Ensures `To OD` is greater than or equal to `From OD` for range rules.
  - Warns about overlapping ranges and duplicate series rules.
  - Dynamically highlights invalid fields with red borders and detailed error badges.

### 3. Excel Integration
- **Export Excel:** Saves the current planner order to a beautifully formatted `.xlsx` spreadsheet, grouping dimensions and calculating total weight.
- **Import Excel:**
  - Upload previous sheets to resume work instantly.
  - Choose to **APPEND** to or **REPLACE** your current active order.
  - Automatically reconstructs custom/modified pipe dimensions and identifies custom cut lengths.

### 4. 100% Self-Contained
- The application runs entirely from a single file: `index.html`.
- No servers or databases to configure.
- Runs completely offline (except for fetching the Excel helper library `SheetJS` from a CDN on first export/import).

---

## 💻 How to Run

Since the application is serverless, running it is simple:
1. **Double-click** the `index.html` file to open it directly in any modern browser (Chrome, Safari, Edge, Firefox).
2. Works on **Windows, macOS, Linux, and mobile devices**.

---

## 📤 Sharing the App

Because it is a single-file application, you can distribute it using any of the following methods:
- **Direct File Sharing:** Email or WhatsApp the `index.html` file (only ~80KB).
- **Network Drives:** Place the file in a shared office folder or NAS.
- **Static Hosting:** Drag and drop the file onto [Netlify Drop](https://app.netlify.app/drop) or host it on **GitHub Pages** for a free public web link.

---

## 🗂 Project Structure

```text
├── index.html          # Core application (UI, styles, logic, and pipe database)
├── pipe_data.json      # Raw JSON database (source reference)
├── pipe_data_embed.js  # JavaScript database export
└── README.md           # Documentation
```

*Note: All local spreadsheet calculations/worksheets (`.xlsx`, `.xls`) are excluded from repository version control.*
