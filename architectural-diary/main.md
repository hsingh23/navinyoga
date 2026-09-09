# Architectural Diary — Navin Yoga Bali landing page

## Overview

This repository is a single-file static website: one `index.html` containing all
markup, styles, and scripts. It was built on 2024-10-16 in three commits and has
had no code changes since. In September 2026 documentation was added and the
commit messages were cleaned up via a messages-only history rewrite (file
contents untouched).

## Timeline

- **2024-10-16 — `67d01f4` feat: add Alien RealTalk landing page with UFO evidence report.**
  The repo began life as something else entirely: a one-page "Alien RealTalk"
  article arguing there is no credible evidence of aliens on Earth. Self-contained
  HTML with inline CSS, minified single-line markup, a `base href` pointing at
  `alien-realtalk.com`. It was placeholder/demo content that established the
  single-file, zero-tooling approach.

- **2024-10-16 — `d0f33c8` feat: replace index.html with Navin Yoga Bali landing page.**
  The whole page was replaced with the yoga studio site that lives here today:
  Apple-style design system (CSS variables, SF Pro stack, frosted fixed header),
  anchor nav, hero, about, benefits, classes, testimonials, and contact sections;
  GSAP hero animations, IntersectionObserver fade-ins, smooth scrolling, a
  scroll-aware header, and a client-rendered class schedule. Markup was reformatted
  from one minified line to readable HTML.

- **2024-10-16 — `6315353` fix: correct hero background and add About section yoga images.**
  Imagery fixes: the hero background moved from a broken local `/a/...` path to a
  hosted Imgur URL, the About photo was swapped, and a second yoga photo was added.

- **2026-09-08 — docs pass.** Added README, AGENTS.md, CHANGELOG, this diary, and
  `prompt.md`. Rewrote the three original commit messages (which referenced the
  wrong project or said just "wi") via `git filter-branch --msg-filter`; trees were
  verified byte-identical before force-pushing `main` with lease.

## Shape of the system

There is no architecture in the software sense — deliberately. One HTML file the
owner can edit with any text editor and host anywhere. The only moving parts are
a GSAP script tag and ~60 lines of vanilla JS (observer, schedule render,
animations, scroll handlers) plus remote Imgur imagery.

## Open issues / future directions

- `/book-class` CTA has no target page.
- Unstyled `benefits-grid` / `class-item` markup.
- Remote image dependency (Imgur) can rot.
- Footer year frozen at 2023.

See `decisions/` for the individual decision records.
