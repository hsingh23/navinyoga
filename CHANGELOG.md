# Changelog

All notable changes to this project. Newest first.

> **History note (2026-09-08):** commit messages in this repository were improved
> via a messages-only history rewrite (trees and file contents untouched). Hashes
> referenced below are the post-rewrite hashes; the work itself dates to 2024-10-16.

## 2024-10-16

### 6315353 — fix: correct hero background and add About section yoga images

- Point the hero background at a hosted Imgur image instead of the broken local `/a/` path.
- Swap the About section photo for a new image.
- Add a second yoga photo below the About paragraph.

### d0f33c8 — feat: replace index.html with Navin Yoga Bali landing page

- Swap the Alien RealTalk placeholder content for a Navin Yoga Bali studio landing page.
- Add fixed anchor nav, hero, about, benefits, online classes, testimonials, and contact sections.
- Render the class schedule dynamically in JS from a hardcoded array.
- Add IntersectionObserver fade-ins, GSAP hero animations, smooth scrolling, and a scroll-aware header.
- Restyle with CSS variables in an Apple-like design and reformat markup from minified to readable HTML.

### 67d01f4 — feat: add Alien RealTalk landing page with UFO evidence report

- Introduce a self-contained `index.html`: an evidence-based report arguing no credible proof of aliens on Earth.
- Cite NASA astrobiology findings and Pentagon UAP report conclusions.
- Include sections on sighting misidentification, debunking cover-up claims, and unverified evidence (Viking 1976, Wow! signal 1977).
- Inline CSS only; no build tooling or other assets.
