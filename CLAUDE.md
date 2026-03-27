# anchorexperience.com — Marketing Site

## Project Context
Static marketing website for ANCHOR Experience — the public-facing brand site at anchorexperience.com. Built by Nathan Luu & Chloe Magick. This is a simple HTML/CSS site, no build step required.

## Architecture
- **Pure static site:** HTML5, CSS3 — no JavaScript framework, no bundler
- `base.css` — CSS reset and base styles
- `style.css` — Full site styles including dark mode support
- **Deployment:** Cloudflare Pages, auto-deploys from `main` branch
- **No build command** — files served as-is from root

## Design System — MANDATORY
- **Palette:** Teal primary (#0d9488), cream secondary — dark mode support
- **Headings font:** Zodiak
- **Body font:** Satoshi
- **Responsive design** required for all changes
- **Performance-first:** No heavy JS, optimise all images (WebP preferred)

## Domain Language
- "Experiences" NOT "events"
- "Journeys" NOT "funnels"
- "Facilitators" NOT "staff"
- "Participants" NOT "attendees"
- ANCHOR Protocol: Assess, Navigate, Create, Harmonise, Orchestrate, Reflect

## Deployment
Push to `main` → Cloudflare Pages auto-deploys globally. No manual steps needed.

## Related Repos
- `anchor-experience` — Full app codebase including AnchorOS dashboard
