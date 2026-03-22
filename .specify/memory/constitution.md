# anchorexperience.com Constitution

## Core Principles

### Static-First Performance
This is a static marketing site. No JavaScript frameworks. HTML5 + CSS3 only. Every page must achieve a Lighthouse performance score of 95+ on mobile. No render-blocking resources.

### ANCHOR Brand Consistency
All visual elements must align with the ANCHOR brand: teal/cream colour palette, Zodiak for headings, Satoshi for body text. Dark mode support is mandatory. No off-brand colours, fonts, or imagery.

### Mobile-First Responsive
All layouts are designed mobile-first. Breakpoints: 320px (mobile), 768px (tablet), 1024px (desktop). No horizontal scrolling at any viewport. Touch targets minimum 44x44px.

### Conversion-Focused Content
Every page must have a clear call-to-action. The 3 Pillars Assessment is the primary conversion mechanism. Content speaks to business owners, coaches, and leaders seeking transformative retreat experiences.

### Cloudflare Edge Optimised
Deployment is exclusively via Cloudflare Pages from the main branch. Leverage Cloudflare's edge caching. All assets must be optimised: WebP images, minified CSS, no unused styles.

## Technical Standards

- No JavaScript frameworks (React, Vue, etc.) — vanilla JS only where needed
- CSS custom properties for theming (dark mode toggle)
- Semantic HTML5 elements throughout
- All images: WebP with PNG fallback, lazy-loaded below fold
- No external fonts loaded from CDN — self-host Zodiak and Satoshi
- No cookies or tracking without explicit consent banner

## Content Guidelines

- Retreat industry language: "experiences", "journeys", "transformation"
- Australian English spelling (colour, optimised, centre)
- Tone: warm, professional, aspirational
- No stock photos — use AI-generated or original retreat imagery

## Governance

All content and design changes reviewed by Nathan Luuber or Chloe Magick before deployment.

**Version**: 1.0 | **Ratified**: 2026-03-23 | **Last Amended**: 2026-03-23
