# Navin Yoga Bali — Landing Page

A single-page marketing site for **Navin Yoga Bali**, a yoga studio offering online
classes "in the heart of Bali's serenity". The entire site is one self-contained
`index.html` with inline CSS and JavaScript — no build step, no dependencies to
install, no framework.

## What and why

The page introduces Yogi Navin's teaching (about, philosophy, benefits), lists the
online class schedule, shows student testimonials, and provides contact details.
It exists to give the studio a fast, zero-maintenance web presence that can be
hosted anywhere static files are served (GitHub Pages, Netlify, an S3 bucket, ...).

## Features

- Apple-inspired design language: CSS custom properties, SF Pro system font stack, frosted-glass fixed header
- Hero section with call-to-action and GSAP entrance animations (GSAP 3.9.1 via CDN)
- Scroll-triggered fade-ins using `IntersectionObserver`
- Online class schedule rendered client-side from a JS array (class, time, instructor)
- Testimonials and contact sections (email + Instagram links — see the contact section of `index.html`)
- Smooth-scrolling anchor navigation and scroll-aware header background
- Mobile-responsive layout via a `max-width: 768px` media query

## Stack

- Plain HTML5 / CSS3 / vanilla JavaScript — one file
- [GSAP](https://gsap.com/) 3.9.1 loaded from cdnjs (only external script)
- Imagery hosted on Imgur (hero background + About-section photos)

## Quickstart

No install or build step. Serve the directory with any static server:

```sh
python3 -m http.server 8000
# or: npx serve
```

Then open <http://localhost:8000>. Opening `index.html` directly in a browser
also works; animations and images require internet access for the CDN and Imgur.

## Structure

```text
.
├── index.html   # the entire site: markup, styles, and scripts inline
├── CHANGELOG.md
├── AGENTS.md
├── prompt.md
└── architectural-diary/
```

## Environment variables

None. The site has no configuration, secrets, or server component.

## Notes

- The "Reserve Your Spot" button links to `/book-class`, which does not exist yet — it will 404 until a booking route/page is added.
- The `benefits-grid`, `benefit-item`, and `class-item` classes are used in markup/JS but have no CSS rules; the benefits grid therefore renders as plain stacked blocks.
- Hosted-on-Imgur images are an external dependency and can disappear independently of this repository.
