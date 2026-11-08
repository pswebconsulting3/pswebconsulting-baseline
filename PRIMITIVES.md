# Primitives and recommended defaults

The full menu of approved values, the way Figma "primitives" work. **Nothing here is a project decision.** Each client design system picks from these tables at kickoff (`KICKOFF.md`); anything not asked uses the **Default** column.

Values in `tokens.css`. Device columns are **Desktop / Tablet (≤1024) / Mobile (≤767)** — the three fields Elementor gives you.

---

## 1. Spacing

4px base unit, 8px rhythm. Token name = px value.

| Token | px | Typical use |
|---|---|---|
| `--space-2` | 2 | Hairline offsets |
| `--space-4` | 4 | Icon-to-text in tight UI |
| `--space-8` | 8 | Inside small controls, label → input |
| `--space-12` | 12 | Eyebrow → heading, inline groups |
| `--space-16` | 16 | Heading → text, paragraph gap |
| `--space-20` | 20 | Mobile gutter |
| `--space-24` | 24 | Card padding (tablet/mobile), form field gap |
| `--space-32` | 32 | Card padding (desktop), text → buttons, 3-up gap |
| `--space-40` | 40 | Desktop gutter, mobile section padding |
| `--space-48` | 48 | Section header → content |
| `--space-56` | 56 | — |
| `--space-64` | 64 | Mobile section padding |
| `--space-80` | 80 | Tablet section padding |
| `--space-96` | 96 | Desktop section padding |
| `--space-112` | 112 | — |
| `--space-128` | 128 | Loose desktop section |
| `--space-160` | 160 | Airy desktop section |
| `--space-192` / `240` | 192 / 240 | Editorial breathing room |

### Rhythm inside a section (fixed)

| Relationship | Value |
|---|---|
| Eyebrow → heading | 12 |
| Heading → paragraph | 16 |
| Paragraph → paragraph | 16 |
| Text → buttons | 32 |
| Button → button | 12 |
| Label → input | 8 |
| Field → field | 24 |
| Section header → section content | Density preset (48 / 40 / 32 balanced) |

Rule: related things close, unrelated far. Use one step or three, never one-and-a-half.

---

## 2. Layout

### Content width

| Option | Value | When |
|---|---|---|
| Narrow | 1140px | Elementor default; text-led brochure sites |
| **Standard — Default** | **1200px** | Most sites |
| Generous | 1280px | Image-led, portfolio, e-commerce with 4-up grids |
| Wide | 1440px | Feature sections only, never body content |
| Reading | 720px | Blog posts, legal pages, long forms |

Content width excludes the side gutter. A 1200px site at 1440px screen = 1200 content + gutters.

### Gutter (side padding)

| | Desktop | Tablet | Mobile |
|---|---|---|---|
| **Default** | 40 | 32 | 20 |
| Options | 32 – 64 | 24 – 40 | 16 – 24 |

Never under 16px on mobile. Elementor's default 10px is too tight.

### Breakpoints

| Set | Points | When |
|---|---|---|
| **Elementor core — Default** | Tablet ≤1024 · Mobile ≤767 | Most sites |
| Extended | + Laptop ≤1366 · Widescreen ≥2400 | Dense layouts that break on 13" laptops; very large screens |

Desktop-first `max-width` queries, matching Elementor. Test at 320, 375, 390, 768, 1024, 1280, 1440, 1920.

### Grid

12 columns. Card grids use the column-count classes below.

### Card gaps by column count (density preset)

| Columns | Compact | **Balanced — Default** | Airy |
|---|---|---|---|
| 2-up | 24 / 16 / 16 | **32 / 24 / 16** | 48 / 32 / 24 |
| 3-up | 24 / 16 / 16 | **32 / 24 / 16** | 40 / 32 / 24 |
| 4-up | 16 / 16 / 16 | **24 / 24 / 16** | 32 / 24 / 16 |

### Column collapse

| Desktop | Tablet | Mobile |
|---|---|---|
| 2 | 2 | 1 |
| 3 | 2 | 1 |
| 4 | 2 | 1 |
| 4 small items (logos, stats) | 4 | 2 |
| 6 small items | 3 | 2 |

### Section padding (top and bottom, density preset)

| Variant | Compact | **Balanced — Default** | Airy |
|---|---|---|---|
| Tight | 48 / 40 / 32 | **64 / 48 / 40** | 80 / 64 / 48 |
| Standard | 64 / 56 / 48 | **96 / 80 / 64** | 128 / 96 / 80 |
| Loose (hero, statement) | 96 / 80 / 64 | **128 / 96 / 80** | 160 / 128 / 96 |

Two sections on the same background collapse the shared padding.

### Card padding (density preset)

| Compact | **Balanced** | Airy |
|---|---|---|
| 24 / 20 / 16 | **32 / 24 / 24** | 40 / 32 / 24 |

### Header

| | Desktop | Tablet | Mobile | Options |
|---|---|---|---|---|
| Header height | **80** | 72 | 64 | 64 / 72 / 80 / 96 |
| Logo height | **40** | 36 | 32 | 32 – 56 |

Mobile menu from tablet down. Anchor links offset by header height + 16.

---

## 3. Typography

### Type scale presets (px)

| Role | Compact ≈1.2 | **Standard ≈1.25 — Default** | Expressive ≈1.333 | Line height | Tracking |
|---|---|---|---|---|---|
| Display | 56 / 48 / 40 | **72 / 56 / 44** | 96 / 72 / 48 | 1.1 | −0.02em |
| H1 | 48 / 40 / 32 | **56 / 44 / 36** | 72 / 56 / 40 | 1.1 | −0.02em |
| H2 | 36 / 32 / 28 | **40 / 32 / 28** | 48 / 40 / 32 | 1.15 | −0.01em |
| H3 | 28 / 24 / 22 | **32 / 28 / 24** | 36 / 32 / 28 | 1.2 | −0.01em |
| H4 | 22 / 20 / 18 | **24 / 22 / 20** | 28 / 24 / 22 | 1.3 | 0 |
| H5 | 18 / 18 / 16 | **20 / 18 / 18** | 22 / 20 / 18 | 1.4 | 0 |
| H6 | 16 / 16 / 16 | **18 / 16 / 16** | 18 / 18 / 16 | 1.4 | 0 |

### Body (body-size preset)

| Role | **16 — Default** | 18 (reading-heavy) | Line height |
|---|---|---|---|
| Lead | 20 / 18 / 18 | 22 / 20 / 18 | 1.5 |
| Body | **16 / 16 / 16** | 18 / 16 / 16 | 1.6 |
| Small | 14 | 14 | 1.5 |
| Caption / eyebrow | 12 | 12 | 1.4 |

Never body under 16px. Never form input text under 16px (iOS zooms).

### Font size primitives

12 · 14 · 16 · 18 · 20 · 22 · 24 · 28 · 32 · 36 · 40 · 44 · 48 · 56 · 64 · 72 · 80 · 96 · 120

### Line length

| | Default | Readable range |
|---|---|---|
| Body | 68ch | 60 – 75ch |
| Headings | 22ch | 18 – 26ch |

### Weights

300 · 400 · 500 · 600 · 700 · 800. Defaults: heading 600, body 400, strong/button 600. Load at most 4 weights in total.

### Families

Up to two families (heading + body). One family for everything is allowed. Mono is optional, for data or code only.

---

## 4. Radius presets

One preset per project. Small exceptions are fine (a pill badge in a sharp site).

| Element | Sharp (0–4) | **Soft (8–12) — Default** | Round (16+, pill buttons) |
|---|---|---|---|
| Button | 2 | **8** | pill |
| Input | 2 | **8** | 12 |
| Card | 4 | **12** | 24 |
| Image | 0 | **12** | 24 |
| Badge / tag | 2 | **4** | pill |
| Modal | 4 | **16** | 24 |
| Inner (nested) | 0 | **8** | 16 |

Nested rule: inner radius = outer radius − padding between them.

Primitives: 0 · 2 · 4 · 6 · 8 · 12 · 16 · 20 · 24 · 32 · full

---

## 5. Elevation

### Shadow primitives

| Token | Value | Use |
|---|---|---|
| `--shadow-1` | 0 1px 2px | Resting card (subtle) |
| `--shadow-2` | 0 2px 8px | Header condensed, dropdown |
| `--shadow-3` | 0 8px 24px | Card hover |
| `--shadow-4` | 0 16px 40px | Floating panel |
| `--shadow-5` | 0 32px 72px | Modal |

Tinted with the darkest neutral, never pure black.

### Elevation presets

| Role | Flat (borders only) | **Subtle — Default** | Lifted |
|---|---|---|---|
| Card | none | **1** | 2 |
| Card hover | none | **3** | 4 |
| Header (scrolled) | none | **2** | 2 |
| Dropdown | 2 | **3** | 4 |
| Modal | 4 | **5** | 5 |

### Borders

1px default · 1.5px nav underline · 2px emphasis (featured pricing) · 3px editorial rule (quote).

---

## 6. Controls

| | Small | **Medium — Default** | Large |
|---|---|---|---|
| Button height | 40 (44 on mobile) | **48** | 56 |
| Button padding x | 16 | **24** | 32 |
| Button text | 14 | **16** | 18 |
| Button icon | 20 | 20 | 20 |
| Input height | — | **48** | — |
| Input text | — | **16** | — |

Touch-target floor: 44 × 44px for anything tappable.

---

## 7. Icons

12 · 16 · 20 · 24 · 32 · 40 · 48 · 64

| Use | Size |
|---|---|
| Inline with text, in buttons | 20 |
| Small UI (chevrons, close) | 16 – 20 |
| Feature / service icons | 32 – 48 |

One icon set per site, matched to the font's stroke weight. Inline SVG preferred.

---

## 8. Images

### Aspect ratios

| Ratio | Default use |
|---|---|
| 16:9 | Hero, video, wide banner |
| 21:9 | Ultra-wide banner |
| 3:2 | Blog cards, general cards |
| 4:3 | Galleries, case studies |
| 1:1 | Products, avatars, Instagram |
| 4:5 | Portrait hero, team, fashion products |
| 2:3 / 3:4 | Tall portrait |

### Export sizes

| Use | Width (1×) | Width (2×) | Target file size |
|---|---|---|---|
| Full-bleed hero | 1920 | 2560 | ≤ 250 KB |
| Content image | 1200 | 2000 | ≤ 150 KB |
| Card | 800 | 1200 | ≤ 80 KB |
| Thumbnail | 400 | 800 | ≤ 40 KB |
| Logo | SVG | SVG | — |

WebP (or AVIF) at quality 75–82. Always set width/height or aspect-ratio to prevent layout shift.

---

## 9. Motion (fixed — not per project)

| Duration | ms | Use |
|---|---|---|
| `--dur-instant` | 90 | Checkbox, toggle |
| `--dur-fast` | 180 | Hover, focus, colour |
| `--dur-base` | 280 | Dropdown, accordion, tooltip |
| `--dur-slow` | 480 | Scroll reveal, card entrance |
| `--dur-slower` | 700 | Hero sequence |
| `--dur-page` | 900 | Page transition, orchestrated intro |

| Easing | Use |
|---|---|
| `--ease-standard` | State changes |
| `--ease-out` | Entrances |
| `--ease-in` | Exits |
| `--ease-spring` | A deliberate pop |
| `--ease-editorial` | Long reveals |

Stagger 40 / 80 / 140ms. Reveal travel 24px (40px max).

Motion *temperature* is a project choice (restrained / moderate / expressive) — it decides how many of these are used, not which values.

---

## 10. Z-index

base 0 · raised 10 · sticky 100 · header 200 · dropdown 300 · overlay 400 · modal 500 · toast 600
