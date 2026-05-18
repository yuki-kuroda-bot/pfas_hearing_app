# Security Notes

## Current Security Model

This is a local HTML app.

- It is not published on the internet.
- It does not send data to an external server.
- It does not require login.
- It stores records in browser `localStorage`.
- PC browsers and mobile browsers do not share this storage automatically.
- PC/mobile sharing currently uses JSON export and JSON import.
- Outside-visit mobile use stores customer data only in the phone browser unless the user exports JSON.

## Main Risk

The main risk is not internet exposure.

The main risks are:

- Someone else using the same computer and browser.
- Exported files being shared outside the company.
- JSON backup files being sent through unsafe channels.
- Customer names, hearing notes, or sales memos being committed to GitHub by mistake.

## Handling Customer Data

Do not commit these files to GitHub:

- CSV exports
- Excel exports containing customer data
- JSON exports or backups
- Screenshots containing customer names
- Sales notes with private customer information

Use `data/`, `exports/`, and `backup/` only for local private files.
These folders are ignored by `.gitignore`.

## Recommended Operation

1. Keep the GitHub repository private.
2. Commit only app code and empty templates.
3. Keep real customer data outside GitHub.
4. Export data only when necessary.
5. Store exported data in a protected local or internal folder.
6. Use only approved internal methods when moving JSON files between PC and mobile.
7. When opening the app from a phone, use `start_mobile_browser_share.command` instead of a normal folder-wide web server.

## Safe Mobile Browser Sharing

`start_mobile_browser_share.command` starts a limited local browser server.

It serves only:

- `index.html`
- `manifest.json`
- `sw.js`

It does not serve:

- `data/`
- `exports/`
- `backup/`
- `docs/`
- `templates/`

Use this only on a trusted Wi-Fi network.
Stop it when mobile use is finished.

## Future Internal Web App

If this app becomes a shared internal web app, add:

- Login
- User permissions
- HTTPS
- Server-side database
- Backup policy
- Operation logs
- Access control for Excel and CSV exports

## GitHub Pages Or Static Hosting

It is acceptable to host only the app files if the user approves publishing the app itself.

Do not host or commit:

- JSON exports
- CSV exports
- Excel exports
- Customer names
- Hearing notes
- Sales notes
- Screenshots with customer information
