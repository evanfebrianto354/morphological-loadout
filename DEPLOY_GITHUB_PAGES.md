# Morphological Loadout V0.4 — Beginner Online Deployment Guide

## Recommended hosting: GitHub Pages
This app is a static HTML/CSS/JavaScript site, so GitHub Pages is a better fit than Google Apps Script for the current version. No server is required.

## Very important: there are TWO kinds of data
1. **Published app files**: `index.html`, `assets/`, `published-state.js`. These live on GitHub and are visible to anyone who opens the link.
2. **Local working data**: builds, sketches, and photos changed with **Replace Photo** are stored in the browser using IndexedDB. They survive code updates on the same website/browser, but do not automatically appear on another device.

V0.4 adds **Publish State** to bridge the two. It downloads a `published-state.js` snapshot containing your current builds, sketches, and local image replacements. Upload/replace that one file on GitHub when you want the public link to show the same state to fresh visitors.

## First-time upload to GitHub Pages
1. Create/sign in to a GitHub account.
2. Create a new repository, for example `morphological-loadout`. Use **Public** if you are on GitHub Free and want GitHub Pages.
3. Extract `Morphological_Loadout_V0.4.zip`.
4. In the new repository choose **Add file → Upload files**.
5. Upload the CONTENTS of the extracted folder, not the outer folder itself. At repository root you should see:
   - `index.html`
   - `published-state.js`
   - `assets/`
   - `README.txt` / this guide
6. Commit the upload.
7. Open **Settings → Pages**.
8. Under **Build and deployment**, choose **Deploy from a branch**.
9. Select branch `main` and folder `/(root)`, then Save.
10. Wait a few minutes. GitHub will show the public URL, usually `https://USERNAME.github.io/morphological-loadout/`.

## Moving your existing V0.3 data to the online site
Before changing versions/URLs:
1. Open V0.3 locally.
2. Click **Export** and save the JSON backup.
3. Open your new GitHub Pages URL.
4. Click **Import** and choose the JSON file.
5. Check your builds and replaced photos.
6. Click **Publish State**. The app downloads `published-state.js`.
7. In GitHub, upload that `published-state.js` and replace the old one.

Now a fresh browser opening the public link will use that published snapshot as its initial state.

## Updating the website later without losing photos/builds
Code revision only:
- Replace/upload the new `index.html`.
- Leave `published-state.js` and `assets/` untouched.
- Your published snapshot and files remain intact.

Data/image revision:
- Work in the app normally.
- Click **Publish State** again.
- Replace only `published-state.js` on GitHub.

Asset-file revision:
- Upload the new image into `assets/` using the SAME filename if you want to replace it.
- If you move/rename an asset file that `index.html` references, the path will break until the code is updated. So treat the `assets/` folder and filenames as stable.

## Why your Replace Photo images do not need a file path
Photos changed through **Replace Photo** are compressed and stored as data inside the app state, not as a normal `C:\...\photo.jpg` file reference. Therefore moving the original image on your PC does not break that already-saved override.

## Presentation safety checklist
- Open the GitHub Pages link once before presenting.
- Import your latest JSON if needed.
- Publish/replace `published-state.js` before the presentation if you want the link to work correctly in a fresh browser.
- Keep the exported JSON as emergency backup.
- Also keep the extracted V0.4 folder offline as a fallback.
- Hard refresh after GitHub updates: Ctrl+F5.
