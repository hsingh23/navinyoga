# One-shot recreation prompt — Navin Yoga Bali landing page

Give this prompt to a coding agent (or a human developer) to recreate this
website from scratch in a single pass.

---

Create a single-file static landing page for "Navin Yoga Bali", a yoga studio
offering online classes. Everything — HTML, CSS, and JavaScript — must live in
one `index.html` with no build step, no framework, and no local image assets.

## Requirements

**Structure** (in order):
1. Fixed `<header>` with centered anchor nav: About, Benefits, Online Classes, Testimonials, Contact.
2. `#hero` — full-width background image, white text with subtle text-shadow, an `h1` "Elevate Your Practice with Yogi Navin", a supporting line about yoga in Bali's serenity, and a pill CTA "Explore Classes" linking to `#classes`.
3. `#about` — heading "About Navin Yoga", two full-width rounded photos (use placeholder hosted images), and a paragraph blending ancient wisdom with modern techniques.
4. `#benefits` — heading "The Navin Yoga Difference" and four blocks: Mind-Body Harmony, Stress Resilience, Enhanced Vitality, Mindful Living, each with one sentence.
5. `#classes` — intro line plus a `#class-schedule` container left empty in markup; JS renders it from an array of four classes: Vinyasa Flow (Mon/Wed/Fri 9:00 AM GMT+8, Navin), Gentle Hatha (Tue/Thu 10:30 AM GMT+8, Ayu), Power Yoga (Mon/Fri 5:00 PM GMT+8, Navin), Yin Yoga (Wed/Sat 4:00 PM GMT+8, Made). CTA "Reserve Your Spot" pointing at `/book-class`.
6. `#testimonials` — two rounded quote cards (Emma S., UK; David L., Canada) praising instruction depth and the online platform.
7. `#contact` — email mailto link and Instagram link (use the addresses already in any existing copy, or plausible placeholders).
8. Footer: "© 2023 Navin Yoga Bali. All rights reserved."

**Design** — Apple marketing-page language:
- CSS custom properties for colors; primary `#0071e3`, light section bg `#f5f5f7`, text `#1d1d1f`.
- System font stack starting `-apple-system`/SF Pro Display; body line-height 1.47059; negative letter-spacing on headings.
- Frosted fixed header: translucent white + `backdrop-filter: saturate(180%) blur(20px)`; opacity increases slightly after 50px scroll (JS).
- CTA: pill radius (980px), white text, hover darkens to `#0077ed`.
- Content column: 90% width, 980px max-width; sections padded 100px; testimonial cards 18px radius on the light background.
- Mobile media query at 768px: nav stacks vertically, hero padding reduced.

**Behavior** (vanilla JS + GSAP):
- Load GSAP 3.9.1 from cdnjs.
- Sections with class `fade-in` start invisible (opacity 0, translateY 20px) and become visible once when 10% visible, via `IntersectionObserver` (unobserve after reveal).
- GSAP staggers hero `h1`, `p`, and CTA entrance (opacity 0 → 1, y 50 → 0, delays 0.2/0.4/0.6).
- All in-page anchor clicks use `scrollIntoView({ behavior: "smooth" })`.
- Header background opacity bumps from 0.8 to 0.9 past 50px of scroll.

**Quality bar:**
- Readable, two-space-indented HTML; double-quoted attributes; `<!DOCTYPE html>` and viewport meta.
- No console errors; page works when opened directly from the filesystem (animations/images need internet).
- Do not invent extra pages, routing, or build tooling.

## Verification

Open the file in a browser (or `python3 -m http.server`): all six anchors
scroll smoothly, the schedule lists four classes, sections fade in on scroll,
the hero animates once, and the layout holds below 768px width.
