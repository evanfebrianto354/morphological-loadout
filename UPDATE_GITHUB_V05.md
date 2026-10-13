# Updating your GitHub Pages site to Morphological Loadout V0.5

Your public site has three different kinds of files:

- `index.html` = the software / UI / logic.
- `assets/` = default packaged images used by the app.
- `published-state.js` = the public snapshot of your own builds, replaced photos, and uploaded sketches.

Do not treat them as the same thing.

## A. Update V0.4 -> V0.5 without losing your work

1. Open your current online V0.4 on the laptop where your latest work exists.
2. Click **Export** and keep the JSON as an emergency backup.
3. Download and extract the V0.5 ZIP.
4. In GitHub, open your `Morphological-Loadout` repository.
5. Choose **Add file -> Upload files**.
6. Upload the V0.5 `index.html` to the repository root. Because the path/name is the same, commit it as the new version of `index.html`.
7. Do **not** delete your existing `published-state.js`.
8. Do **not** delete your existing `assets/` folder.
9. Commit the change.
10. Wait for GitHub Pages to deploy, usually a short time.
11. Open the public URL and hard-refresh once (`Ctrl+Shift+R`) if necessary.

Your old V0.4 `published-state.js` is compatible enough for V0.5 and will continue to load.

## B. Publish new photos, sketches, and builds

When your current browser contains changes that you want everyone to see:

1. Save the build normally in the app.
2. Click **Publish State**.
3. The app downloads a new `published-state.js`.
4. In GitHub, **Add file -> Upload files**.
5. Drag the new `published-state.js` into the repository root.
6. GitHub will treat the same pathname as a changed file; commit the change.
7. Wait for Pages to redeploy.
8. Test in Incognito or another device.

You do not need to upload the original JPG/PNG used in **Replace Photo** or **Upload Sketch**. Those images are embedded into `published-state.js` as compressed data URLs.

## C. What is the `assets/` folder for?

`assets/` contains only the default images that are referenced by paths such as:

`assets/nautilus.jpg`

Those files must exist on GitHub or the default card image will be broken.

Upload the full `assets/` folder once. After that, only change it when you intentionally add/replace a packaged default asset.

Using **Replace Photo** inside the web app does not write into this folder.

## D. Do I need JSON Import on the classroom computer?

No, not for the public/presentation version.

If `published-state.js` is correctly committed to GitHub, V0.5 loads it automatically on a fresh browser/device. Your classroom computer should only need the public URL.

JSON **Export/Import** is for:
- backup,
- transferring an unpublished working state,
- recovering from mistakes.

It is not part of the normal presentation workflow.

If a computer somehow shows an older local copy, open the **Current Build** dropdown and choose **Reload published version**.

## E. Why did V0.4 sometimes keep showing the old state?

V0.4 could prefer an existing browser-local IndexedDB state, and `published-state.js` could also be cached. V0.5 improves this by:

- requesting `published-state.js` with a cache-busting URL;
- comparing published/local timestamps;
- providing **Reload published version**.

## Recommended presentation setup

Public URL = primary.

Also keep:
- one recent Export JSON in your Drive/USB;
- one extracted offline V0.5 folder on your laptop.

That gives you public, backup, and offline fallback.
