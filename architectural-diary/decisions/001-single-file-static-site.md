# ADR 001 — Keep the site as a single self-contained HTML file

- **Date:** 2024-10-16 (established), reaffirmed 2026-09-08
- **Status:** Accepted

## Context

The site is a small marketing page for a yoga studio. There is no content
pipeline, no team of frontend developers, and no need for shared components.

## Decision

All markup, styles, and scripts live in one `index.html`. No bundler, no
framework, no package.json, no install step.

## Consequences

- Anyone can open the file and edit it; hosting is trivially static.
- Zero supply-chain surface beyond one CDN script.
- Page-level scalability is limited — a second page would force a choice between
  duplication and introducing shared assets/build tooling.
- CSS and JS accumulate inline; discipline needed to keep sections readable.
