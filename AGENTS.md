# AGENTS.md

Guidance for coding agents working in this repository.

## What this is

A single-file static landing page for Navin Yoga Bali. Everything — markup,
styles, and scripts — lives in `index.html`. There is no package.json, no build
system, no test suite, and no server component.

## Commands

```sh
# Serve locally (pick one):
python3 -m http.server 8000
npx serve

# View history:
git log --oneline
```

There is nothing to install, lint, or build. To verify changes, serve the
directory and open http://localhost:8000 in a browser (internet access needed
for the GSAP CDN and Imgur images).

## Architecture map

`index.html` is organized, top to bottom:

1. `<style>` block — CSS custom properties (`:root`), base typography, header/nav,
   hero, testimonial, image, and button styles; one mobile media query.
2. `<body>` markup — fixed `<header>` nav, then `<main>` sections:
   `#hero`, `#about`, `#benefits`, `#classes`, `#testimonials`, `#contact`, plus footer.
3. `<script>` blocks — GSAP 3.9.1 from cdnjs, then inline JS:
   - `IntersectionObserver` fade-in for `.fade-in` sections
   - hardcoded `classes` array rendered into `#class-schedule`
   - GSAP hero entrance animations
   - smooth-scroll handlers for anchor links
   - scroll listener that darkens the header background

## Conventions

- Keep everything in `index.html`; do not introduce build tooling for minor edits.
- Styles go in the single `<style>` block; scripts in the inline `<script>` block.
- Use conventional commit messages (`feat:`, `fix:`, `docs:`, ...).
- Two-space indentation, double-quoted HTML attributes.

## Gotchas

- `/book-class` (the "Reserve Your Spot" CTA) points to a route that does not
  exist; it 404s until a booking page is added.
- `benefits-grid`, `benefit-item`, and `class-item` have no CSS rules — the
  benefits grid and schedule render unstyled. Add rules if visual polish is wanted.
- Images and the GSAP script are remote (Imgur, cdnjs). The page degrades
  (no animations, missing images) when offline; don't "fix" this by inlining
  large assets without asking.
- The class schedule is a hardcoded JS array, not data fetched from anywhere.
- Footer copyright says 2023; update if that matters.

## Verifying changes

1. `git diff` — confirm only `index.html` (or docs) changed.
2. Serve locally and click through every nav anchor; check the console for JS errors.
3. Resize below 768px to confirm the mobile layout still works.
4. Confirm fade-in animations still trigger on scroll.

## Pointers

- `CHANGELOG.md` — per-commit history (newest first), including a note about the
  2026-09-08 messages-only history rewrite.
- `architectural-diary/` — how the site evolved and the decisions behind it.
- `prompt.md` — a one-shot prompt that recreates this site from scratch.
