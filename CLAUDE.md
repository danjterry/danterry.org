# danterry.org

Dan Terry's personal coaching / consulting / speaking site. Plain static site, no build step.
Hosted on Netlify, which deploys automatically from the `main` branch of this repo.

## How edits work
1. Edit files directly (all page content lives in `index.html`).
2. Commit and push to `main`. Netlify publishes within a minute or two.

## Layout
- `index.html`: the whole site. Markup and copy are near the top; the page logic (navigation between
  Home / About / Services / Topics / Testimonials / Work, the inquiry form, chip options) is in the
  `<script type="text/x-dc">` block at the bottom.
- `assets/img/`: photos and background textures (`dan-speaking.jpg`, `dan-portrait.jpg`,
  `texture-light.png`, `texture-dark.png`).
- `assets/fonts/`: self-hosted Hanken Grotesk and Newsreader.
- `assets/js/dc-runtime.js`: generated runtime that renders the page (loads React from unpkg).
  Do not edit by hand.
- `forms.html`: hidden copy of the inquiry form so Netlify Forms detects it. Keep its fields in sync
  with the form in `index.html`. Do not delete.
- `start`: an older bundled copy of the site, kept as-is.

## Rules
- Never use em dashes in site copy.
- Keep the inquiry form's `name="inquiry"` and field names unchanged unless forms.html is updated too.
