# BRÖD — Design System

Retro, two-color letterpress bakery identity. Warm, hand-drawn, always-running charm. We sell sourdough. (Owner-pinned; applies to all Bröd Bread surfaces including this CRM dashboard.)

## Color
- Bakehouse Red `#C41D12` — headlines, mascot, primary buttons, urgent/warn states.
- Sky Blue `#5597CD` — accents, tags, links, secondary strokes, tagline, info states.
- Cream Paper `#F8EFEB` — default background for everything.
- Ink Brown `#2B1A15` — keylines, text, hard shadows.
- Soft Ink `#5B463E` — body copy, secondary text (on cream only).
- Blue Tint `#EEF5FB` — panel tint.
- Two inks on cream. Never gradients as color fills, never full color on the mascot.

## Typography
- Display/titles: Unbounded 700–900 (600 for subheads). ~72px hero, 36px section, 20px subtitle.
- Body/UI/labels: IBM Plex Sans 400–700, 16px body.
- Spec captions/codes/labels: IBM Plex Mono 500, 12px, `.14em` letter-spacing, uppercase.
- Thai text falls back to system Thai faces (Sarabun / Noto Sans Thai) — Unbounded/Plex have no Thai glyphs; numerals and Latin render in the brand faces.

## Retro treatment
- Thick keylines: 3px `#2B1A15` borders on cards, badges, buttons.
- Hard offset shadows: `box-shadow: 8px 8px 0` ink brown (or faint tint), no blur. Primary buttons press down into their shadow on hover.
- Halftone dots: `radial-gradient` dot fields for texture (subtle, cream surfaces).
- Diagonal stripes: `repeating-linear-gradient` 45° — awning edges, in-progress fills.
- Sunburst rays: `repeating-conic-gradient` behind the hero, faint red on cream.
- Rounded pill shapes, dashed circular stamps, starburst badges, slight rotations (±1–2°) on stickers/stamps.
- Max 1–2 background colors per surface.

## Components
- Buttons: pill, 3px ink border. Primary = red fill cream text; secondary = blue outline (fills on hover); tertiary = underline link.
- Tags/chips: pill; active = red fill, inactive = blue outline; neutral = ink outline.
- Inputs: pill, 3px ink border, cream/white field.
- Price stamp: red dashed circle, Unbounded price.
- Panels/cards: cream body, 3px ink keyline, hard 8px offset shadow; optional red header bar.

## Mascot rules
- `brod-mascot.png` — Crumb, running left → right, paired with wordmark.
- Don't recolor, drop-shadow, stretch, skew, or rotate the artwork.
- One ink only in reproductions: red on cream, cream on red, or blue on cream.
- Clear space ~ one bun-height; never below 44px tall.

## Voice
Warm, playful, unfussy. Short and friendly — reads like a hand-stamped label. UI copy stays in Thai on the CRM; brand marks (BRÖD, tagline) stay Latin.
