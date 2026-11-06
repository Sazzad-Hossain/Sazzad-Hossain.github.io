# sazzad.dev Portfolio — Frontend Rules

## Stack reality (never violate)
- Static HTML/CSS/JS. No framework, no build step, no npm runtime deps.
- Files: index.html, architecture-hrm.html, architecture-pos.html
- Only external dep: Google Fonts. Everything else inline.

## Grounding
- Read ./DESIGN.md before any UI change. Use ONLY tokens defined there.
- Colors/fonts/radii change centrally in :root — never hardcode inline values.

## Quality rules (Vercel Web Interface Guidelines)
- Gradient text is forbidden; accent color is always SOLID var(--cyan)
  (.grad-text class does this — do not reintroduce background-clip:text)
- Min hit target 24×24px; 44×44px for primary CTAs on mobile
- Never disable zoom (no user-scalable=no / maximum-scale=1)
- Visible :focus-visible state on every interactive element
- prefers-reduced-motion support is mandatory (exists — don't break it)
- No emoji as feature icons — inline SVG only
- Async actions must show a pending state (none exist currently — mailto/tel links only)
- Reveal animations must be gated behind html.js — a JS error must never hide content

## QA loop
- After any change: screenshot at 1440px AND 375px viewport
- Verify: no overflow, no text overlap, nav works, arch pages print-clean

## Deploy
- Netlify Drop / GitHub Pages (Sazzad-Hossain.github.io). Static — never add a build step.