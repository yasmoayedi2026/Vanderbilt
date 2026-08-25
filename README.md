# Learnings from Vanderbilt — Interactive Presentation

A single-file interactive HTML slide deck (`index.html`) built from the *Learnings from Vanderbilt — Heart Transplant Site Visit, April 2026* presentation. No dependencies, no build step — all images and charts are embedded.

## Publish on GitHub Pages

1. Create a new repository on GitHub (e.g. `vanderbilt-learnings`). Public is simplest; a private repo works on GitHub Pro/Team.
2. Add `index.html` (and this README) to the repo, then commit and push:
   ```bash
   git init
   git add index.html README.md
   git commit -m "Add interactive Vanderbilt learnings deck"
   git branch -M main
   git remote add origin https://github.com/<your-username>/vanderbilt-learnings.git
   git push -u origin main
   ```
   Or just drag-and-drop `index.html` onto the repo page in the browser ("Add file → Upload files").
3. In the repo go to **Settings → Pages**. Under *Build and deployment* set **Source: Deploy from a branch**, **Branch: main / (root)**, and save.
4. After a minute the deck is live at `https://<your-username>.github.io/vanderbilt-learnings/`.

Because it is a single file you can also open `index.html` directly from disk, attach it to an email, or drop it on a USB stick.

## Presenting

| Key / action | What it does |
|---|---|
| → / Space / click right side | Reveal next bullet, then next slide |
| ← / click left edge | Previous slide |
| A | Reveal everything on the current slide |
| O | Slide overview grid (click any slide to jump) |
| N | Toggle presenter notes panel |
| F | Fullscreen |
| Home / End | First / last slide |
| Swipe | Navigate on touch devices |

Other interactive elements: hover the bars and dots on the PGD charts for year-by-year numbers; hover or tap the big stat tiles for context; click the tabs on the preoperative slide; click the REUP vs DCD diagram to enlarge; click items on the action-item checklist to tick them off (saved in the viewer's browser).

Each slide has its own URL (`#s4`, `#s12`, …) so you can link directly to a slide.

## Editing

Everything lives in `index.html`. Slides are `<section class="slide">` blocks in order; presenter notes are in the `notes` object near the top of the `<script>`; chart data is in the `nonsev`, `sev` and `died` arrays.
