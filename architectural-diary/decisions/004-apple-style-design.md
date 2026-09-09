# ADR 004 — Follow an Apple-style design language

- **Date:** 2024-10-16
- **Status:** Accepted

## Context

The page needed a calm, premium feel appropriate for a Bali yoga brand, without
a design system or framework.

## Decision

The `d0f33c8` rebuild adopted Apple-marketing-page conventions:

- CSS custom properties for colors (`--primary-color: #0071e3`, etc.)
- `-apple-system` / SF Pro font stack with Apple's line-height and letter-spacing values
- Fixed header with `backdrop-filter: saturate(180%) blur(20px)` frosted glass
- Pill-shaped CTA (`border-radius: 980px`), 980px max content width
- Generous 100px section padding, large tight-tracking headings

## Consequences

- A recognizable, polished look from pure CSS.
- `backdrop-filter` is progressive enhancement; older browsers get a translucent
  header without blur.
- The aesthetic is strongly identified with Apple; diverging later means changing
  the custom properties, which is cheap because they are centralized.
