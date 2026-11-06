# DESIGN.md — sazzad.dev Portfolio

## Brand feel
Dark, premium, modern-tech. Engineer aesthetic. Glassmorphism, no clutter.

## Colors (source of truth — also in :root of index.html)
--bg: #0F172A | --bg-deep: #090D16
--surface: rgba(30,41,59,.55) | --surface-2: rgba(30,41,59,.85)
--border: rgba(148,163,184,.15)
--text: #F8FAFC | --muted: #94A3B8
--cyan: #38BDF8 | --indigo: #6366F1 | --purple: #A855F7 | --teal: #2DD4BF
--grad: linear-gradient(135deg,#38BDF8 0%,#6366F1 55%,#A855F7 100%)
Teal = success/online status only. Rose = decorative window dots only.

## Typography
Headings: Sora 600–800, tracking -.02em to -.03em
Body: Inter 400–600, 16.5px/1.65
Code/labels/chips: JetBrains Mono 400–500
H1: clamp(2.4rem,5.6vw,4rem) · H2: clamp(1.9rem,4vw,2.7rem)

## Spacing & layout
Container 1140px max, 24px gutter · Section padding 104px (78px mobile)
Card padding 26–30px · Grid gaps 14–56px

## Radius / effects
Cards 18px · Buttons 12px · Chips 999px · Icons 12–15px
Glass = blur(14px) on --surface · Primary glow = 0 10px 40px rgba(99,102,241,.35)
Grid overlay: 56px cells, 6% opacity, masked fade to 62% height

## Motion
Reveal: translateY(26px)→0, .7s ease, stagger via --d
Blobs: 24–34s alternate drift, restrained opacity · Typing: 78ms type / 38ms delete
MUST respect prefers-reduced-motion (already implemented)

## Icons & buttons
Inline SVG only, stroke 2, currentColor, 17–22px
Primary btn = gradient bg + white text + glow · Ghost = glass + border, hover → cyan

## Anti-slop policy (MANDATORY — Impeccable / Vercel WIG)
- Gradient TEXT is forbidden anywhere (headlines, numbers, links, footer).
- Accent pattern: solid #F8FAFC headline + ONE word in solid #38BDF8 (.grad-text renders this).
- Gradients allowed ONLY on: primary button bg, logo mark, progress bar, timeline, card top border.
- Icons: inline SVG only — emoji tiles forbidden.
- Min hit target 24×24px; 44×44px on primary mobile CTAs. Zoom must never be disabled.
- Every interactive element: :focus-visible outline (2px cyan, 3px offset).
- JS-failure safety: hide-until-scroll styles are gated behind html.js — content must
  ALWAYS display if JavaScript breaks.