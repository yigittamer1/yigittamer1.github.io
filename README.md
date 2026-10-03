# yigittamer1.github.io

Public GitHub Pages site for yigittamer1's apps — privacy policies, terms,
support pages, and share/universal-link landing pages. Served at
`https://yigittamer1.github.io/`.

**This repo is public and so is its commit history.** Never commit an API
key, `.p8` key, certificate, or any other secret here — removing a file
later does not remove it from history.

## Layout

- `index.html` — portfolio landing page listing the apps.
- `<app>/` — one folder per app (`sudoku/`, `metrik/`,
  `Xpensebudgetmanager/`), each holding that app's `index.html` (privacy
  policy), `terms.html`, `support.html`, and — for apps that support
  share links — a `p/` landing page for people without the app.
- `.well-known/apple-app-site-association` — the universal-link
  association file for **all** apps on this domain. Each app's entry lives
  side by side in this one file; adding a new app's universal links means
  adding an entry here, not replacing it.
- `.nojekyll` — tells GitHub Pages to serve dotfiles/dot-folders (like
  `.well-known/`) as-is instead of running them through Jekyll, which
  ignores anything starting with a dot by default.
- `app-ads.txt` — **belongs to multiple apps, not just one.** Don't edit
  or remove entries without checking which app they serve; ask first if
  unsure.

## Per-app notes

### `sudoku/`

Source of truth for Sudoku's public pages (the app repo, `sudoku`, used to
keep a duplicate `web/` copy — deleted because two copies drift). Pages are
edited and pushed here directly, not generated from the app repo.

- `index.html` — privacy policy (no separate `privacy.html`).
- `terms.html` — custom EULA (the app links to this instead of Apple's
  standard EULA, so it must keep Apple's four minimum required terms).
- `support.html` — required by App Store Connect as the Support URL.
- `p/` — share-link landing page; redirects to the App Store on iOS after
  a few seconds, carries Safari's app-clip banner, switches language by
  browser locale.

Both English and a full Turkish translation live in each file, split
under an `<h1 id="tr">` anchor. Keep section counts equal on both sides —
a block edit that only touches one language is a silent content bug.

**These pages describe the app's current behavior as a promise** (what it
collects, whether it shows ads, etc.). Whenever the app's capabilities
change, update the matching page in the same change — see the `sudoku` app
repo's `PROJECT_PLAN.md` for what's currently true.

### `metrik/`, `Xpensebudgetmanager/`

Same pattern (privacy/terms/support for each app). Not actively documented
here beyond that — see each app's own repo for what's current.

## Related repo

`sudoku` (private) is this app's source code. Its own README points back
here for anything related to the public pages.
