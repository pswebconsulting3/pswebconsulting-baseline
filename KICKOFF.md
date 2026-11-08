# Kickoff — structural questions for every client design system

Asked at the start of every new client design system, after the brief. Each answer maps to a token or preset in `tokens.css`. **If a question is skipped, the default is used** — so the designer can confirm the whole list in one go.

Creative direction (references, signature element, mood, copy) lives in `BRIEF-TEMPLATE.md`. This file is structure only.

---

## Round A — Layout

| # | Question | Options | Default | Sets |
|---|---|---|---|---|
| A1 | Content width | 1140 · 1200 · 1280 | **1200** | `--content-width` |
| A2 | Breakpoint set | Elementor core · Extended (+ laptop 1366, widescreen 2400) | **Core** | media queries + Elementor Site Settings |
| A3 | Side gutter | Standard 40/32/20 · Tight 32/24/16 · Generous 64/40/24 | **Standard** | `--gutter-d/t/m` |
| A4 | Density | Compact · Balanced · Airy | **Balanced** | `data-density` (section padding, card gaps, card padding) |

## Round B — Type

| # | Question | Options | Default | Sets |
|---|---|---|---|---|
| B1 | Type scale | Compact · Standard · Expressive | **Standard** | `data-type-scale` |
| B2 | Body size | 16 · 18 on desktop | **16** | `data-body-size` |
| B3 | Families | Client's own · We choose (Google Fonts or licensed web fonts) | — | `--font-heading`, `--font-body` |
| B4 | One family or two | One · Two | **Two** | `--font-heading` = `--font-body` if one |
| B5 | Heading weight | 500 · 600 · 700 | **600** | `--weight-heading` |

## Round C — Shape and surface

| # | Question | Options | Default | Sets |
|---|---|---|---|---|
| C1 | Radius preset | Sharp · Soft · Round | **Soft** | `data-radius` |
| C2 | Elevation | Flat · Subtle · Lifted | **Subtle** | `data-elevation` |
| C3 | Button size | Medium 48 · Large 56 for primary CTAs | **Medium** | `--button-height-md` |

## Round D — Header and images

| # | Question | Options | Default | Sets |
|---|---|---|---|---|
| D1 | Header height | 64 · 72 · 80 · 96 | **80 / 72 / 64** | `--header-height-d/t/m` |
| D2 | Header style | Solid sticky · Transparent over hero, solid on scroll · Static | **Solid sticky** | `.hb-header--overlay` |
| D3 | Card image ratio | 3:2 · 4:3 · 1:1 · 4:5 | **3:2** | `--ratio-card` |
| D4 | Product image ratio (Woo) | 1:1 · 4:5 · 3:4 | **1:1** | `--ratio-product` |

## Round E — Motion

| # | Question | Options | Default |
|---|---|---|---|
| E1 | Motion temperature | Restrained · Moderate · Expressive | **Moderate** |
| E2 | Orchestrated moment | Hero line reveal · Hero media reveal · Scroll-driven section · None | **Hero line reveal** |
| E3 | Smooth scroll (Lenis) | No · Yes | **No** |

---

## Output — paste into the client's `brand.css`

```css
/* <Client> — project tokens. Generated from KICKOFF.md answers. */
/* <html data-density="balanced" data-type-scale="standard"
         data-body-size="16" data-radius="soft" data-elevation="subtle"> */
:root {
  --content-width: var(--width-1200);
  --gutter-d: var(--space-40); --gutter-t: var(--space-32); --gutter-m: var(--space-20);
  --header-height-d: var(--space-80); --header-height-t: 72px; --header-height-m: var(--space-64);
  --weight-heading: var(--font-weight-600);
  --ratio-card: var(--ratio-3-2);
  --ratio-product: var(--ratio-1-1);

  /* Brand layer */
  --font-heading: "…";
  --font-body: "…";
  --color-primary: #…;
  /* … every --color-* in the brand layer */
}
```

Record every answer in the brief's Decisions log. Any later override (e.g. one section needs a wider gap) is made as a project token, never by editing the baseline.
