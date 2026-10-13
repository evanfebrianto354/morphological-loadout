Morphological Loadout V0.4

NEW IN V0.4
- Library display modes: Large / Medium / Small.
- Medium: each component category stays on one fixed row.
- Small: all components become one compact game-inventory grid with images only and no library scrolling.
- Selected Components now show mini stat bars, not only numbers.
- Online publishing helper: Publish State downloads `published-state.js`.
- `published-state.js` is separate from `index.html`, so future UI/code revisions can be uploaded without overwriting the published builds/images snapshot.

LOCAL USE
Open index.html in Chrome/Edge. Existing V0.3 local data should remain compatible because V0.4 keeps the same IndexedDB database name. Still export a JSON backup before upgrading.

ONLINE USE
Read DEPLOY_GITHUB_PAGES.md.
