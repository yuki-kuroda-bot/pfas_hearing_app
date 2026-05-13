# PFAS Hearing App

## Purpose

This app supports customer hearing for PFAS-entry environmental sales.

It is designed for:

- Customer-by-customer hearing records
- A/B/C customer classification
- PFAS, sludge dewatering, nutrient control, and equipment opportunity checks
- Simple analysis graphs
- CSV, Excel, JSON, and print output

## Files

| Path | Purpose |
|---|---|
| `index.html` | Main app file |
| `docs/pfas_hearing_app_manual.pptx` | User manual slide deck |
| `templates/pfas_hearing_analysis_template.xlsx` | Excel analysis template |
| `.gitignore` | Prevents customer data and exports from being committed |
| `CHANGELOG.md` | Change history |
| `SECURITY.md` | Security and data-handling notes |

## How To Use

1. Open `index.html` in a browser.
2. Click `新規` to create a customer record.
3. Enter customer information and hearing answers.
4. Use `A/B/C` classification to decide the next action.
5. Use `Excel出力` or `CSV出力` only when needed.

## Data Storage

The app stores input data in the browser's `localStorage`.

This means:

- Data is not sent outside automatically.
- Data stays in the same browser on the same computer.
- If another person can use the same computer and browser, they may see the saved data.
- Exported CSV, Excel, and JSON files may contain customer information and must be handled carefully.

## GitHub Policy

Safe to put in GitHub:

- `index.html`
- `docs/`
- `templates/`
- `README.md`
- `CHANGELOG.md`
- `SECURITY.md`
- `.gitignore`

Do not put in GitHub:

- Real customer data
- CSV exports
- Excel exports with real customer information
- JSON backups
- Sales notes containing customer names or private information

Use a private repository if this app is uploaded to GitHub.

