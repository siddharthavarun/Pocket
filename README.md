# Pocket Ledger

A monthly spending tracker you install on your phone from the browser. Log expenses by category, subcategory and who paid, set limits, and see where the month went on a category-coloured ring.

## What's in here

| File | What it does |
| --- | --- |
| `index.html` | The whole app. Built from `../pocket-ledger.html` by `../build.py`; don't edit it directly |
| `manifest.webmanifest` | Name, icons and colours used when the app is installed |
| `sw.js` | Lets the app open offline. `build.py` bumps `VERSION` on every build |
| `icons/` | Home-screen and browser icons |

## Your data

Everything is saved on the phone, in the browser's storage. Nothing is uploaded.

- The app and the Pocket Ledger page in Claude keep **separate** data. To move your ledger into the app:
  1. In Claude, open Pocket Ledger, go to **Manage → Backup → Download backup (.json)**.
  2. In the app, go to **Manage → Import**, choose that file, and pick **Replace my ledger** (or **Add to my ledger**).
- Back up from **Manage → Backup** now and then. The page shows when you last did.
- If you delete the app or clear the browser's site data, anything not backed up is gone.

## Publish on GitHub Pages

1. Create an empty public repository at <https://github.com/new>, for example `pocket-ledger`. Don't add a README or licence.
2. From this `app` folder, replacing `YOUR-USERNAME`:

   ```bash
   git init -b main
   git add -A
   git commit -m "Pocket Ledger app"
   git remote add origin https://github.com/YOUR-USERNAME/pocket-ledger.git
   git push -u origin main
   ```

3. In the repository, open **Settings → Pages**, choose **Deploy from a branch**, then **main** and **/ (root)**, and click **Save**.
4. After a minute or two the app is live at `https://YOUR-USERNAME.github.io/pocket-ledger/`.

## Install it on your phone

- **iPhone:** open the link in Safari, tap **Share**, then **Add to Home Screen**.
- **Android:** open the link in Chrome, then tap **Install app** (or ⋮ → **Add to Home screen**).

## Updating the app

1. Edit `../pocket-ledger.html`.
2. Run `python3 ../build.py` from this folder (or `python3 build.py` from the folder above).
3. Commit and push. Installed apps show "A new version is ready" the next time they're opened online.

## Try it locally

```bash
python3 -m http.server 8125
```

Then open <http://localhost:8125>.
