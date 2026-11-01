# ClipSetuu — Vercel Ready (Updated, Static Version)

This is the updated Vercel-ready, static version of ClipSetuu.
There is no server, no database, no install step, and no build step.
Do NOT use the old fullstack code pack for Vercel — that one fails
because it needs a Muse-only runtime library, which only exists
inside Muse. This ZIP has no `package.json`, no `bun.lock`, no
server code, no `node_modules`, no database, and no space-sdk or
`file:` dependency.

## What is inside this ZIP

After unzipping, you will see one folder: `clipsetuu-vercel-ready/`

Inside that folder:

- `index.html` — the whole ClipSetuu app
- `assets/` — logo and hero images the page needs
  - `assets/logo-mark.png`
  - `assets/logo-full.png`
  - `assets/hero-valley.webp`
- `privacy-policy/index.html` — Privacy Policy page
- `terms/index.html` — Terms of Service page
- `p/terms/index.html` — Terms alias, same page at `/p/terms`
- `README.md` — this file

The legal pages use single slashes only:
`/privacy-policy`, `/terms`, and `/p/terms`.
There is no double slash (`//`) in any of these links.

## What is new in this update

- Footer links on every page: Home, Privacy Policy, Terms.
- The legal pages above, so Google OAuth links resolve.
- Start-clip fix: an uploaded video now loads in the Studio
  at 00:00, and Clip #1 starts at 00:00:00. A short video
  shorter than the selected clip length becomes one
  whole-video clip, from the start to the end.

## ⚠️ Very important warning

Upload `index.html` AND the whole `assets/` folder AND the
`privacy-policy/`, `terms/`, and `p/terms/` folders TOGETHER.

If you upload only `index.html` alone, the logo and hero image
will break (blank / broken images), because the page loads them
from `assets/`, and the Privacy Policy and Terms pages will
not open. Do not upload only the HTML file. Do not rename
any folder. Keep the names exactly as they are.

## Step 1: Unzip

1. Download this ZIP file.
2. Right-click it and choose Extract All (Windows) or
   double-click it (Mac). On mobile, use your Files app
   and choose Extract.
3. Open the folder. You should see `index.html`, `assets/`,
   `privacy-policy/`, `terms/`, and `p/` inside
   `clipsetuu-vercel-ready/`.

## Step 2: Upload to GitHub

1. Go to github.com and sign in.
2. Click New repository. Name it `clipsetuu` (double-u).
   Keep it Public or Private — either works for Vercel.
3. Click Create repository.
4. Click "uploading an existing file" / Upload files.
5. Open the unzipped `clipsetuu-vercel-ready/` folder.
   Drag `index.html`, the whole `assets/` folder, the
   `privacy-policy/`, `terms/`, and `p/` folders, and
   this `README.md` into the GitHub upload area.
   IMPORTANT: upload the CONTENTS of the folder to the
   repo root (the main page of the repo). Do not upload
   a folder inside a folder, and do not upload the ZIP
   file itself.
6. Click Commit changes.
7. Check the repo main page. You must see `index.html`,
   `assets`, `privacy-policy`, `terms`, and `p` right
   there at the top level. If you see
   `clipsetuu-vercel-ready` as a folder inside the repo,
   the files are one level too deep — move them to root.

## Step 3: Deploy on Vercel

1. Go to vercel.com and sign in with GitHub.
2. Click Add New, then Project.
3. Find your `clipsetuu` repository and click Import.
4. Framework Preset Other — choose **Other**.
5. Build Command empty — leave it **empty** (delete anything in
   it). Output Directory: leave it empty / default.
   Install Command: leave it empty. There is nothing to
   install — this version has no `package.json` on purpose.
6. Click Deploy and wait until it says Ready.
7. Open the link Vercel gives you, for example
   `clipsetuu.vercel.app`. Test the page there, and open
   `/privacy-policy`, `/terms`, and `/p/terms` too.

If Vercel asks about a build or shows an install error,
stop and check Step 2 and Step 3 again: the repo root
must have `index.html` + `assets/` + the legal folders,
Preset must be Other, and Build Command must be empty.

## Honest limits of this version

Please read this before you share the link:

- Login is a DEMO flow. "Continue with Google" and Email
  OTP do not sign you into a real Google account. Saved
  Clips are saved only in your own browser (localStorage).
- YouTube / Instagram upload is a DEMO flow. The modal
  prepares the title, caption, hashtags and cover, and
  shows upload progress, but it does NOT post to a real
  YouTube or Instagram account. Real posting needs real
  OAuth connections — a separate Phase 2 backend step.
- Clip export is done in your browser: MP4 where the
  browser supports it, otherwise WebM-to-MP4 conversion
  in the browser, with WebM as a fast fallback. Long
  clips take more time and memory. Nothing is uploaded
  to a server.
- A YouTube link gives a title/thumbnail preview only.
  To make a real clip from your own footage, upload a
  video file. A link alone cannot clip real footage in
  this static version.

## Quick test after deploy

1. Open the Vercel link. Logo and hero image must show.
2. Open the footer Privacy Policy and Terms links.
3. Upload a short video file. Clip #1 must start at
   00:00:00 and the Studio player must start at 00:00.
4. Generate clips, switch a caption style, and edit a
   thumbnail hook.
5. If any image is broken, re-check the `assets/`
   upload in Step 2 first.
