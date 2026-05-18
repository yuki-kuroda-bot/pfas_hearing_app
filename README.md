# PFAS Hearing App

## Purpose

This app supports customer hearing for PFAS-entry environmental sales.

It is designed for:

- Customer-by-customer hearing records
- A/B/C customer classification
- Sales stage, budget timing, and estimated opportunity tracking
- PFAS, sludge dewatering, nutrient control, and equipment opportunity checks
- Simple analysis graphs
- Mobile-friendly list/input/dashboard switching
- JSON import/export for moving data between PC and mobile
- CSV, Excel, JSON, and print output

## Files

| Path | Purpose |
|---|---|
| `index.html` | Main app file |
| `manifest.json` | Mobile install settings |
| `sw.js` | Offline cache for browser/PWA use |
| `icons/` | App icon for mobile home screen |
| `start_mobile_browser_share.command` | Starts safe local browser sharing for mobile access |
| `tools/safe_mobile_server.py` | Serves only app files, not customer data folders |
| `docs/pfas_hearing_app_manual.pptx` | User manual slide deck |
| `templates/pfas_hearing_analysis_template.xlsx` | Excel analysis template |
| `.gitignore` | Prevents customer data and exports from being committed |
| `CHANGELOG.md` | Change history |
| `SECURITY.md` | Security and data-handling notes |

## How To Use

1. Open `index.html` in a browser.
2. Click `新規` to create a customer record.
3. Enter customer information and hearing answers.
4. Enter sales stage, budget timing, estimated opportunity, and next action.
5. Use `A/B/C` classification to decide the next action.
6. Use `Excel出力` or `CSV出力` only when needed.
7. Use `JSON出力` and `JSON読込` to move records between PC and mobile.

## PC And Mobile Sharing

This app does not automatically sync customer data through the internet.

For outside visits, use the mobile browser version:

1. Open the deployed app URL on the phone.
2. Add it to the home screen.
3. Enter hearing records on the phone.
4. After returning to the office, use `JSON出力` on the phone.
5. Use `JSON読込` on the PC.

To open the app from a phone:

1. Connect the PC and phone to the same trusted Wi-Fi.
2. On the PC, open `start_mobile_browser_share.command`.
3. Open the displayed `http://...:8765/` URL on the phone.

The safe mobile server serves only:

- `index.html`
- `manifest.json`
- `sw.js`

It does not serve:

- `data/`
- `exports/`
- `backup/`
- `docs/`
- `templates/`

Safe sharing method:

1. On the PC, click `JSON出力`.
2. Move the JSON file to the phone using an internal, approved method.
3. On the phone, open the app and click `JSON読込`.
4. Select the JSON file.

The JSON file may contain real customer information.
Do not upload it to GitHub or public cloud storage.

## Outside Visit Policy

The deployed app should contain app files only.

Customer data stays in each browser's local storage until the user exports JSON.
Do not commit exported JSON, CSV, Excel, screenshots, or customer notes to GitHub.

## Data Storage

The app stores input data in the browser's `localStorage`.

This means:

- Data is not sent outside automatically.
- Data stays in the same browser on the same computer.
- PC and mobile each have separate browser storage.
- If another person can use the same computer and browser, they may see the saved data.
- Exported CSV, Excel, and JSON files may contain customer information and must be handled carefully.
- Trial customer data and test data are confidential if they contain real names, notes, or sales information.

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
