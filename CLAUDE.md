# danterry.org

Dan Terry's personal coaching / consulting / speaking site. Plain static site, no build step.
Hosted on Netlify, which deploys automatically from the `main` branch of this repo and publishes
only the `site/` folder (set in `netlify.toml`).

## How edits work
1. Edit files in `site/` directly. All page content lives in `site/index.html`.
2. Commit and push to `main`. Netlify publishes within a minute or two.
3. Check the result at https://danterry.org (desktop and phone width).

## Layout
- `site/` (published at danterry.org)
  - `index.html`: the whole site. Markup and copy are near the top; the page logic (navigation between
    Home / About / Services / Topics / Testimonials / Work, the inquiry form, chip options) is in the
    `<script type="text/x-dc">` block at the bottom.
    Pages are linkable by hash (`#about`, `#services`, `#topics`, `#work`); `pageFromHash` and
    `setTitle` handle this. The Testimonials page exists but is unlinked and still has sample quotes. Phone layout rules are in the `@media` block in
    the first `<style>`; their selectors match inline styles as browsers serialize them
    (`margin: 0px auto`, with spaces), so write new ones the same way.
  - `assets/img/`: images used on the site (`dan-speaking.jpg`, `dan-portrait.jpg`,
    `texture-light.png` = limewash, `texture-dark.png` = green textile).
  - `assets/fonts/`: self-hosted Hanken Grotesk and Newsreader.
  - `assets/js/dc-runtime.js`: Claude Design runtime that renders the page (loads React from unpkg).
    Do not edit by hand.
  - `forms.html`: hidden copy of the inquiry form so Netlify Forms detects it. Keep its fields in sync
    with the form in `index.html`. Do not delete.
  - `_redirects`: Netlify redirects (old `/start` page now redirects home).
  - `assets/img/favicon.svg`: browser tab icon.
- `design/` (NOT published): the original Claude Design project, "Danterry Coaching Website Redesign".
  - `Dan Terry.dc.html`: the Claude Design source as of Nov 19 2026. `site/index.html` was built from
    it and is now the working source; this copy is reference only.
  - `uploads/`: all original photos and mood board references (many not yet used on the site).
    To use one, copy it into `site/assets/img/` with a descriptive name.
  - `textures/`: limewash, green-textile, walnut (walnut not yet used).
  - `screenshots/`: design review screenshots.

## Rules
- Never use em dashes in site copy.
- Keep the inquiry form's `name="inquiry"` and field names unchanged unless forms.html is updated too.
- This repo is public. Do not commit private screenshots or credentials.
