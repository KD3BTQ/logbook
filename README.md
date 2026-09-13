# ADIF Log Manager

A single-file, offline-first HAM radio ADIF log editor. Open `index.html`
directly in a browser, or serve it via GitHub Pages (see below) to get the
online callsign lookup working from a real `https://` address instead of a
local file.

## 

## About the online callsign lookup

The "Look up online" button calls the free HamDB.org API directly from
your browser. This requires:

* An actual internet connection at the time you click it.
* HamDB.org's API allowing cross-origin requests from wherever the page is
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

