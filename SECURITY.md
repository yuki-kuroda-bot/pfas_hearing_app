# Security Notes

## Current Security Model

This is a local HTML app.

- It is not published on the internet.
- It does not send data to an external server.
- It does not require login.
- It stores records in browser `localStorage`.

## Main Risk

The main risk is not internet exposure.

The main risks are:

- Someone else using the same computer and browser.
- Exported files being shared outside the company.
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

## Future Internal Web App

If this app becomes a shared internal web app, add:

- Login
- User permissions
- HTTPS
- Server-side database
- Backup policy
- Operation logs
- Access control for Excel and CSV exports

