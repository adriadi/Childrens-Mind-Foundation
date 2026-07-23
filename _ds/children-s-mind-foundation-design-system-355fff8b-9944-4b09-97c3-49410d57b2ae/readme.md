# The Children's Mind Foundation — Design System

## Company & product context

The Children's Mind Foundation (CMF) is a UK-based charity (established by Trust Deed, 8 October 2024, currently progressing through Charity Commission registration) supporting neurodivergent children and young adults up to age 21. It runs community programs — The Kind Classroom (a nurture classroom at St Mary's Primary School, Poole), Discovery Village play sessions, family photoshoots/days out — and fundraises through events like the Ben Nevis trek (#trek4KidsMind) and Run Bournemouth. The brand mascot is **Blue Bear** ("The Bear Who Understands Without Words"), the emotional and visual heart of the org.

There is one product represented here: the **CMF marketing website** (a single-page charity site: hero, mission, programs, Blue Bear story, donate/events, contact).

**Sources provided:**
- A local export of the live marketing site — `index.html`, `styles.css`, `script.js`, plus real photography and logo/badge PNGs. This was read directly and is the ground truth for all tokens, components and the UI kit in this system.
- GitHub repo `adriadi/Childrens-Mind-Foundation` — attempted via `github_get_tree`/`github_read_file`; the repo appears to be **empty** (tree endpoint returns 409, no root files found). Nothing could be imported from it. If this repo is populated later, re-explore it — it may contain a newer/different build worth reconciling with this system.

## Components

Location: `components/<group>/`. All are named exports, paired with a `.d.ts` and a `.prompt.md`.

- **core/**: `Button`, `Eyebrow`, `HashtagRibbon`
- **cards/**: `StatCard`, `PillarCard`, `ProgramCard`, `ActionCard`
- **forms/**: `Input`, `Select`, `Textarea`, `ContactForm`
- **navigation/**: `Navbar`, `Footer`
- **decorative/**: `StarField`

These were enumerated directly from the source site's CSS/markup (buttons, eyebrow pills, stat tiles, pillar/program/action cards, the contact form fields, nav/footer, and the decorative star field) — not invented from a generic component-library template.

**Intentional additions:** none beyond what the source site defines.

## UI kit

`ui_kits/marketing-site/` — a full interactive recreation of the CMF homepage (`index.html` + `Homepage.jsx`), composed entirely from the components above. Covers every section of the source site: nav, hero with star field + hashtag ribbon, colouring-book banner, mission + stats, goals/pillars, programs + photo strip, Blue Bear story, donate/events banners, transparency notice, contact form, footer.

## Foundations

`tokens/` (`colors.css`, `typography.css`, `spacing.css`, `base.css`) imported by root `styles.css`. `guidelines/` holds specimen cards for colors, type, spacing/radius/shadow, and brand motifs (mascot, color-blocking, stars, hashtag banners, photography style, button states).

## Assets

`assets/` — the real logo/badge PNGs (`badge_full.png`, `logo.png`, `favicon.png`) and real community photography (classroom opening, Ben Nevis trek training, Run Bournemouth team). No other logo variants were supplied.

---

## Content fundamentals

**Voice:** warm, gentle, second-person-adjacent but mostly third-person about "children" and first-person-plural ("we") about the org — never clinical or corporate. Sentences are simple and emotionally direct.

**Tone examples from source copy:**
- "The beauty of different minds" (hero headline)
- "You are safe. You are not alone." (Blue Bear's line — repeated verbatim as the emotional core of the brand)
- "Some stars shine brightly from the moment they appear. Others take longer to be seen. Every one of them belongs in the sky."
- "We're a small, volunteer-run team — thank you for your patience and for believing in what we're building." (self-aware, humble, no corporate polish)

**Casing:** sentence case throughout body copy and headings (not Title Case). Eyebrow labels are uppercase small pills ("OUR MISSION") but that's a UI treatment, not a copy convention.

**Person:** mission copy speaks about children in third person ("we help build their confidence"); calls-to-action speak directly to the reader ("Get in touch", "Donate now", "Say hello").

**Emoji:** never used. Hashtags (`#4kidsMind`, `#trek4KidsMind`) stand in for playful shorthand instead.

**Numbers/stats:** used sparingly and honestly — small real numbers ("24 children", "£2,000+", "34 sponsors") rather than inflated claims, consistent with a young, transparent, volunteer-run charity.

**Transparency as a content pattern:** the site repeats its registration status (Trust Deed date, "not yet a registered charity", volunteer trustees drawing no salary) twice — in the hero trust bar and again in a dedicated "A note on transparency" section. Any new copy for this brand should preserve this candor rather than smooth it over.

---

## Visual foundations

**Colors:** Sky Blue (`#41A8F5`) is dominant — logo, hero, nav; Sunset Orange (`#E97132`) is reserved strictly for CTAs (Donate/Contact) and decorative stars; Lime Green (`#92D14F`/`#B9DB3F`) marks secondary banners/hashtags; Deep Navy (`#16324A`) is body text, never pure black. See `guidelines/colors-*.card.html`.

**Type:** Baloo 2 (rounded, playful) for all headlines/display text; Inter for body copy and UI/forms. Loaded via Google Fonts CDN (see Iconography/fonts note below — no local font files were in the source export).

**Backgrounds:** flat color blocks (sky/lime/sunset sections) rather than gradients-as-decoration — the only gradients used are subtle, single-hue depth washes (`linear-gradient(170deg, sky → sky-deep)` on the hero, radial glows behind the Blue Bear story) or dark scrims over photography (never colorful/purple marketing gradients). Photography is real, candid, community-sourced — warm color temperature, un-retouched, no B&W or heavy grain.

**Animation:** minimal and gentle — a slow floating badge (`float-badge`, 6s ease-in-out), a pulsing glow behind Blue Bear (`pulse-glow`, 4s), twinkling hero stars (4s+ staggered), and IntersectionObserver scroll-reveal (fade + 18px rise, 0.6s ease) on most sections. All motion respects `prefers-reduced-motion: reduce`. No bounce/spring easing despite the playful brand — motion is soft, not energetic.

**Hover states:** buttons lift 2px (`translateY(-2px)`) and darken (primary → sunset-deep) or invert (secondary/outline swap fill and text color). Pillar cards lift 6px with a deeper shadow. Nav links get a blue underline. No press/active-shrink state exists in the source.

**Shadows:** soft, warm-tinted navy shadows only (`rgba(22,50,74,…)`), never black — `shadow-card` for resting cards, `shadow-soft` for elevated/floating elements, plus a dedicated warm-orange shadow under primary buttons.

**Corners:** generously rounded, never sharp — 10px (inputs), 18px (stat tiles), 28px (cards, photos, art panels), full pill (buttons, eyebrows). The one intentional exception is the hashtag ribbon, which uses a small 8px radius and a -1° rotation for a "hand-placed sticker" feel.

**Cards:** white fill, 1px hairline border in `--line` (a pale blue, not gray), soft navy shadow, generous rounding — never a colored left border accent.

**Layout:** classic centered container (max-width 1180px), generous section padding (96px vertical), color-blocked full-bleed sections for emphasis (donate banner, Blue Bear story) alternating with white/cream sections — 1-2 background colors per fold, never more.

**Transparency/blur:** used only for the sticky nav (`backdrop-filter: blur(8px)` over 92%-opacity white) and for translucent "glass" action cards sitting on top of colored banners (`rgba(255,255,255,0.12–0.3)`) — never as a general decorative effect.

---

## Iconography

- **No icon font or SVG icon library is used.** All icons in the source are small hand-authored inline SVGs (social icons, mission-pillar icons, contact-detail icons, transparency-notice shield) — simple 2px-stroke line icons, `24x24` viewBox, `stroke="currentColor"` or a brand hex.
- **No PNG/emoji icons anywhere** — emoji is never used, matching the content voice guidance above.
- **Star motifs** (solid orange + white outline, `M12 2l2.6 6.2 6.7.6…` five-point star path) are the one recurring decorative "icon" — used purely as ambient texture (hero background, section headers), never as a UI/interaction glyph. Reproduced faithfully in `components/decorative/StarField.jsx`.
- No stroke-icon library (Lucide/Heroicons) is referenced by the source; because the inventory is small and bespoke, this system inlines the same hand-picked SVGs rather than substituting a CDN set. If you need additional icons beyond what's here, Lucide (stroke-based, 2px weight) is the closest visual match to the existing hand-authored set — flag any such addition as a substitution.

## Font note

Baloo 2 and Inter are loaded from Google Fonts CDN exactly as the source site does (`tokens/typography.css`). No local `.woff2`/`.ttf` files were present in the provided export, so none are bundled here — this is not a substitution (these are the brand's actual specified fonts), just a CDN-hosted delivery matching the source.

---

## Index

```
styles.css                 → root stylesheet, imports tokens/*
tokens/
  colors.css                → color tokens
  typography.css            → font tokens + Google Fonts import
  spacing.css                → spacing/radius/shadow/motion tokens
  base.css                    → reset + global element styles
components/
  core/       Button, Eyebrow, HashtagRibbon
  cards/      StatCard, PillarCard, ProgramCard, ActionCard
  forms/      Input, Select, Textarea, ContactForm
  navigation/ Navbar, Footer
  decorative/ StarField
guidelines/                  → 16 foundation specimen cards (Colors/Type/Spacing/Brand)
ui_kits/marketing-site/       → index.html + Homepage.jsx (full homepage recreation)
assets/                       → real logo/badge PNGs + community photography
SKILL.md                     → portable Claude Skill wrapper for this system
```

## Caveats & ask

- The attached GitHub repo (`adriadi/Childrens-Mind-Foundation`) appears empty — I could not import anything from it. If that's wrong, please re-share the correct repo/branch and I'll reconcile this system with it.
- No local font files were supplied — Baloo 2/Inter are loaded from Google Fonts CDN, which matches the source site's own approach, so no substitution was needed.
- Only one product (the marketing site) was represented in the source; if there's an app, donor portal, or other CMF surface, share it and I'll build a matching UI kit.
- **Please review the components and homepage recreation and tell me what to refine** — I'd love your eyes on whether the tone/colors feel right, whether any programs/copy need updating, and whether you want additional sections (e.g. a full Events or History page) built out next.
