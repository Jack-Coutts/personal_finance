# Finance Dashboard

Live app: https://jack-coutts.github.io/personal_finance/

A private, browser-based finance dashboard for tracking monthly income, bills, other payments, and savings or investments.

It runs entirely in a single HTML file with no backend, no account system, and no automatic persistence.

## Features

- Import a local JSON file or start with a blank sheet
- Add, edit, and delete entries in each section
- Track both monthly savings amounts and current investment values
- Record an `asOf` date for investment values
- Export data back to JSON
- Print or save a clean PDF report
- Works well on desktop and mobile

## Privacy

This project is intentionally local-first:

- no server
- no database
- no sign-in
- no analytics
- no automatic saving

Data only exists in memory while the page is open, unless the user exports it.

## Usage

1. Open `index.html` in a browser
2. Choose `Start Fresh` or import an existing JSON file such as `example.json`
3. Update the dashboard
4. Export JSON to save changes
5. Use Print to export a PDF snapshot

## Data Format

The app uses JSON so it can store structured finance data cleanly, including current values and valuation dates.

Example top-level structure:

```json
{
  "income": [],
  "other": [],
  "bills": [],
  "savings": [],
  "asOf": "2026-03-12"
}
```

Savings entries can include:

```json
{
  "item": "Cash ISA",
  "amount": 50,
  "currentValue": 2376.08,
  "asOf": "2026-03-12"
}
```

## Hosting on GitHub Pages

This project can be hosted as a static site with GitHub Pages.

1. Create a repository on GitHub
2. Upload `index.html`, `example.json`, `README.md`, and `LICENSE`
3. Open `Settings` -> `Pages`
4. Under `Build and deployment`, choose `Deploy from a branch`
5. Select `main` and `/ (root)`
6. Save

GitHub will publish the site at:

`https://your-username.github.io/your-repo-name/`

## Project Files

- `index.html` - the full application
- `example.json` - sample finance data
- `README.md` - project overview and usage
- `LICENSE` - GNU GPL v3
