# ADR 003 — Render the class schedule from a hardcoded JS array

- **Date:** 2024-10-16
- **Status:** Accepted

## Context

The Online Classes section lists four recurring classes (name, time, instructor).
There is no backend and no data source.

## Decision

A `classes` array is declared in the inline script and rendered into
`#class-schedule` via `document.createElement` / `innerHTML` at load time. An
HTML comment marks the mount point.

## Consequences

- Schedule edits are code edits: change the array, redeploy the file.
- No fetch, no CORS, no API key — the page stays fully static.
- Schedule cannot be updated by a non-technical owner without touching JS.
- The generated `.class-item` elements have no CSS rules, so they render as
  plain stacked blocks (a known rough edge).
