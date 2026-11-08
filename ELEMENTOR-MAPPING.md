# Elementor mapping

Where every token goes in Elementor, so a design built on the baseline can be rebuilt pixel-perfect and stay editable for the client.

Load `tokens.css` and `components.css` through the **child theme** (enqueued), not the Custom CSS box. Set the `data-*` preset attributes on `<html>` via the child theme's `header.php` or a `language_attributes` filter.

---

## 1. Site Settings → Layout

| Elementor field | Token | Default |
|---|---|---|
| Content Width | `--content-width` | 1200px |
| Widgets Space | `--gap-stack` | 16px |
| Container padding (Desktop / Tablet / Mobile) | `--gutter-d/t/m` (left/right), `--section-y-d/t/m` (top/bottom) | 40/32/20 · 96/80/64 |
| Breakpoints → Mobile | — | 767 |
| Breakpoints → Tablet | — | 1024 |
| Breakpoints → Laptop (extended set only) | — | 1366 |
| Breakpoints → Widescreen (extended set only) | — | 2400 |

Disable Mobile Extra and Tablet Extra unless the project chose them.

## 2. Site Settings → Global Colors

| Elementor slot | Token |
|---|---|
| Primary | `--color-primary` |
| Secondary | `--color-secondary` |
| Text | `--color-text` |
| Accent | `--color-accent` |
| Custom: Background | `--color-bg` |
| Custom: Surface | `--color-surface` |
| Custom: Surface alt | `--color-surface-alt` |
| Custom: Inverse | `--color-inverse` |
| Custom: On primary | `--color-on-primary` |
| Custom: On inverse | `--color-on-inverse` |
| Custom: Text muted | `--color-text-muted` |
| Custom: Border | `--color-border` |
| Custom: Success / Warning / Error / Info | `--color-success` … |

Keep the custom names identical to the token names (without `--color-`).

## 3. Site Settings → Global Fonts

| Elementor slot | Token |
|---|---|
| Primary | `--font-heading` (H1–H3) |
| Secondary | `--font-subheading` (H4–H6) |
| Text | `--font-body` |
| Accent | `--font-accent` (buttons, labels, eyebrows) |

## 4. Site Settings → Typography

Enter each per device (Desktop / Tablet / Mobile). Values below are the **Standard** type scale with **16** body; use `PRIMITIVES.md` §3 for the other presets.

| Element | Size D/T/M | Line height | Letter spacing | Weight |
|---|---|---|---|---|
| Body | 16 / 16 / 16 | 1.6 | 0 | 400 |
| H1 | 56 / 44 / 36 | 1.1 | −0.02em | 600 |
| H2 | 40 / 32 / 28 | 1.15 | −0.01em | 600 |
| H3 | 32 / 28 / 24 | 1.2 | −0.01em | 600 |
| H4 | 24 / 22 / 20 | 1.3 | 0 | 600 |
| H5 | 20 / 18 / 18 | 1.4 | 0 | 600 |
| H6 | 18 / 16 / 16 | 1.4 | 0 | 600 |
| Link colour | Primary; hover = primary hover | | | |

Create Global Typography styles for: Display, Lead, Small, Eyebrow (uppercase, 12px, 0.1em, 600).

## 5. Site Settings → Buttons

| Field | Token | Default |
|---|---|---|
| Typography | `--font-accent`, `--button-text-md`, `--weight-button` | 16 / 600 |
| Padding | `--button-pad-x-md`, height via vertical padding to reach 48px | 16px 24px |
| Border radius | `--radius-button` | 8 (soft) |
| Background / Text | `--color-primary` / `--color-on-primary` | |
| Hover background | `--color-primary-hover` | |
| Transition | 180ms | |

Secondary and ghost: add the CSS classes `hb-btn hb-btn--secondary` in Advanced → CSS Classes, or save as Global Widgets.

## 6. Site Settings → Form Fields

| Field | Token | Default |
|---|---|---|
| Typography | `--input-text` | 16px |
| Text / Background | `--color-text` / `--color-bg` | |
| Border | `--input-border` `--color-border-strong` | 1px |
| Border radius | `--radius-input` | 8 |
| Padding | 12px 16px (gives 48px height) | |
| Focus border | `--color-focus` | |

## 7. Site Settings → Images

Border radius: `--radius-image`. Hover: none by default (image zoom is a card-level effect).

## 8. Site Settings → Header / Footer (Theme Builder)

- Header height: `--header-height-d/t/m` (80/72/64), logo height `--logo-height-d/t/m` (40/36/32).
- Sticky: Motion Effects → Sticky top, with an "on scroll" CSS class `hb-header--condensed` (via small JS) — not Elementor's height shrink.
- Mobile menu from Tablet down.

## 9. Containers and grids

| Pattern | Elementor setup |
|---|---|
| Section | Container, full width, padding = section-y + gutter, inner Boxed = content width |
| 2-up / 3-up / 4-up | Container → Grid, columns 2/3/4 (tablet 2/2/2, mobile 1), gap = `--gap-grid-*` per device |
| Split | Container → Flex row, 50/50 (or 60/40), stack on mobile, gap = `--gap-grid-2` |
| Section header | Inner container, max width 720, gap 16 |

## 10. What goes in as HTML widgets

- Orchestrated hero sequences (GSAP)
- Scroll-driven sections
- Any component whose motion can't be reproduced natively

Everything else native, so the client can edit text and images. Never combine Elementor Motion Effects with GSAP on one element.

## 11. Performance settings

Elementor → Features: enable Optimized DOM Output, Improved Asset Loading, Improved CSS Loading, Inline Font Icons, Lazy Load Background Images. Disable Google Fonts loading if fonts are self-hosted. Disable Font Awesome / eicons if unused.
