# Desk Board

A todo board (categories, deadlines, and recurring tasks) that installs on your iPhone like an app.
Everything is saved locally on your device — there's no server or account.

## Put it on your iPhone

1. Turn on GitHub Pages for this repo: **Settings → Pages → Source → Deploy from a branch**,
   pick `claude/iphone-todo-webapp-s3grpd` (or `main`, once merged) and folder `/ (root)`, then save.
   GitHub gives you a URL like `https://<username>.github.io/deskcard/`.
2. Open that URL in **Safari** on your iPhone.
3. Tap the Share icon → **Add to Home Screen**.
4. Launch it from the home screen icon — it opens full-screen, no Safari address bar.

## Sync between devices (GitHub Gist)

Your list is stored in the browser on that device (`localStorage`) by default. To keep
several devices in sync, click **Sync** in the toolbar:

1. Create a [personal access token](https://github.com/settings/tokens/new?scopes=gist&description=Desk+Board+sync)
   with just the **gist** scope (the panel has a link that pre-fills this for you).
2. Paste the token into the Sync panel and leave **Gist ID** blank, then click
   **Save connection** — this creates a new private Gist and stores its ID.
3. On your other device, open the Sync panel, paste the *same* token and the
   **Gist ID** shown on the first device, then click **Save connection** — it pulls
   the board down immediately.
4. Turn on **Auto-sync** on each device to push changes automatically after you
   edit, and to pull automatically when you reopen the app or switch back to its tab.
   Otherwise use **Push now** / **Pull now** to sync manually.

Notes on sync:
- The token and Gist ID are stored only in that browser's `localStorage` and are sent
  only to `api.github.com` — never to any other server. They are *not* included in
  **Export**/**Import** backups.
- Sync is last-write-wins: whichever device pushed most recently wins on pull. If you
  edit the same board offline on two devices at once, the later push overwrites the
  earlier one.
- Anyone with the token and Gist ID can read/write your board, so keep the token
  private and revoke it from GitHub's token settings if a device is lost.

## Notes

- Use the **Export** button on the toolbar now and then to save a JSON backup, and
  **Import** to restore it (or move it to another device) — useful with or without Gist sync.
- Works offline after the first load — a service worker caches the app itself.
- No sign-up, no required server, no tracking. Sync is optional and uses your own GitHub account.
