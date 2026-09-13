# ADIF Log Manager

A single-file, offline-first HAM radio ADIF log editor. Open `index.html`
directly in a browser, or serve it via GitHub Pages (see below) to get the
online callsign lookup working from a real `https://` address instead of a
local file.

## Deploying with GitHub Pages

1. Create a new repository on GitHub (public repos get free Pages hosting;
   private repos need a paid plan for Pages).
2. Push this folder's contents to that repository (see commands below).
3. On GitHub, go to the repo's **Settings > Pages**.
4. Under "Build and deployment", set **Source** to "Deploy from a branch".
5. Set **Branch** to `main` (or whichever branch you pushed to) and folder
   to `/ (root)`, then click **Save**.
6. GitHub will build the site (usually takes under a minute) and show you
   the URL, typically:
   `https://<your-username>.github.io/<repo-name>/`

Because the file is named `index.html`, that URL will load the tool
directly - no extra path needed.

## Pushing from the command line

```bash
cd adif-pages-repo
git init
git add index.html README.md
git commit -m "Add ADIF Log Manager"
git branch -M main
git remote add origin https://github.com/<your-username>/<repo-name>.git
git push -u origin main
```

Then enable Pages as described above.

## Updating later

Whenever you edit `index.html` (either locally or by asking Claude to make
changes), just commit and push again:

```bash
git add index.html
git commit -m "Update ADIF Log Manager"
git push
```

GitHub Pages automatically rebuilds within a minute or two of each push.

## About the online callsign lookup

The "Look up online" button calls the free HamDB.org API directly from
your browser. This requires:

- An actual internet connection at the time you click it.
- HamDB.org's API allowing cross-origin requests from wherever the page is
  hosted (GitHub Pages gives it a real domain, which most public APIs are
  more comfortable with than a local `file://` page).

If it still doesn't work after deploying to Pages, that likely means
HamDB's API doesn't allow direct browser-based (CORS) requests at all, and
querying it would need a small server-side proxy (e.g. a Cloudflare Worker)
sitting in front of it - GitHub Pages alone can't add that since it only
serves static files.

Everything else in the tool (creating/editing/saving ADIF files, grid
square math, CQ/ITU zone estimates) works completely offline, on
GitHub Pages or opened locally, with or without this lookup feature.
