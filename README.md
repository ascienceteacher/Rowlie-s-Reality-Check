# Rowlie's Reality Check — GitHub Pages Launcher

This repository is the public GitHub Pages doorway for **Rowlie's Reality Check**.

The actual student app still runs in **Google Apps Script**, where student work can save to Google Sheets. GitHub Pages simply gives you a clean, memorable URL that redirects students to the deployed Apps Script web app.

## Files

- `index.html` — branded Rowlie landing page and redirect
- `config.js` — the only file you need to edit
- `rowlie.png` — Rowlie artwork
- `404.html` — sends mistyped Pages paths back to the home page

## 1. Get your Apps Script Web App URL

In Apps Script:

1. Choose **Deploy → Manage deployments**.
2. Open your current Web App deployment.
3. Copy the **Web app URL**.
4. Make sure you use the deployed URL ending in `/exec`, not the Apps Script editor URL.

## 2. Add the URL to GitHub

Open `config.js` and replace:

```js
const APP_SCRIPT_URL = "PASTE_YOUR_APPS_SCRIPT_WEB_APP_URL_HERE";
```

with your real deployed URL, for example:

```js
const APP_SCRIPT_URL = "https://script.google.com/macros/s/YOUR_DEPLOYMENT_ID/exec";
```

Commit the change.

## 3. Turn on GitHub Pages

In the repository:

1. Go to **Settings → Pages**.
2. Under **Build and deployment**, choose **Deploy from a branch**.
3. Choose the `main` branch and `/ (root)`.
4. Save.

GitHub will give you a Pages address similar to:

`https://YOUR-USERNAME.github.io/REPOSITORY-NAME/`

That is the link you can give students or turn into a TinyURL/QR code.

## Updating the student app later

You usually do **not** need to change this GitHub repository when you update the Apps Script code.

As long as you edit the same Apps Script deployment and create a **new version** under **Manage deployments**, the `/exec` Web App URL normally stays the same. The GitHub launcher will continue pointing to it.
