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

## Notes

- Your list is stored in the browser on that device (`localStorage`). It is *not* synced
  between devices. Use the **Export** button on the toolbar now and then to save a JSON
  backup, and **Import** to restore it (or move it to another device).
- Works offline after the first load — a service worker caches the app itself.
- No sign-up, no server, no tracking.
