# ADR 002 — Load GSAP from a CDN and host imagery on Imgur

- **Date:** 2024-10-16
- **Status:** Accepted

## Context

The page uses GSAP for hero animations and several photographs. Keeping the
repository tiny and binary-free was preferred.

## Decision

- GSAP 3.9.1 is loaded from cdnjs in a `<script>` tag; it is not vendored.
- All images (hero background, About-section photos) are Imgur URLs (fixed in
  `6315353` after an early local-path attempt 404'd).

## Consequences

- Repository stays text-only and small.
- The page requires internet access; offline it loses animations and imagery.
- Availability depends on third parties: if Imgur removes an image or cdnjs is
  blocked, the site degrades independently of this repository.
- Mitigation if needed later: vendor the GSAP file and self-host images.
