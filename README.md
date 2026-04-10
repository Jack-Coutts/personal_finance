# Finance Dashboard

Live app: https://jack-coutts.github.io/personal_finance/

A local-first, browser-based dashboard for tracking monthly `income`, `bills`, and `savings`.

The app runs in a single `index.html` file with no backend, accounts, or automatic persistence.

## Features

- Import finance data from a local JSON file (click or drag-and-drop)
- Start a blank session with `Start Fresh`
- Add and remove entries in three categories: income, bills, savings
- Add optional tags to bills (up to 5 tags per bill)
- View automatic totals and a `Remaining` figure (`Income - Bills`)
- View a `Bills by Tag` summary table with amount + count
- Export current data as JSON, CSV, or Markdown
- Works on desktop and mobile

## Privacy

This project is intentionally local-first:

- no server
- no database
- no sign-in
- no analytics
- no autosave

Data stays in memory for the current browser session unless exported.

## Usage

1. Open `index.html` in a browser
2. Import a JSON file (for example `test-data.json`) or choose `Start Fresh`
3. Add entries using the `+` buttons in each table
4. Use `Export JSON`, `Export CSV`, or `Export MD` to save your data
5. Use `New Session` to return to the landing screen and clear the current in-memory state

## Data Format

The importer expects this top-level structure:

```json
{
  "income": [],
  "bills": [],
  "savings": []
}
```

Each entry must include:

```json
{
  "name": "Monthly Salary",
  "amount": 3500
}
```

Bills can also include optional tags:

```json
{
  "name": "Groceries",
  "amount": 350,
  "tags": ["food", "household"]
}
```

Notes:

- `amount` must be a positive number
- `name` is trimmed and limited to 100 characters
- tags are normalized to lowercase, trimmed, limited to 20 characters each, max 5 tags
- unknown fields are ignored on import
- JSON export also includes a computed `summary` block

## Hosting on GitHub Pages

This project can be hosted as a static site with GitHub Pages.

1. Create a repository on GitHub
2. Upload `index.html`, `test-data.json`, `README.md`, and `LICENSE`
3. Open `Settings` -> `Pages`
4. Under `Build and deployment`, choose `Deploy from a branch`
5. Select `main` and `/ (root)`
6. Save

GitHub will publish the site at:

`https://your-username.github.io/your-repo-name/`

## Project Files

- `index.html` - full application (UI, logic, styling)
- `test-data.json` - sample data for import testing
- `README.md` - project documentation
- `LICENSE` - GNU GPL v3
