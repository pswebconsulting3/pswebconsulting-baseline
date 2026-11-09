# PS Web Consulting — House Baseline

The foundation every PS Web Consulting website is built on. It holds the best-practice primitives (spacing, sizing, widths, type, radii, shadows, motion), the presets a project picks from, the standard component set, page structures per site type, and the quality checklist — so no project starts from a blank page.

Brand (logo, colours, fonts, imagery, copy) is never stored here. It comes from each client.

## Files

| File | What it is |
|---|---|
| `DESIGN-SYSTEM.md` | The rules, and how the three tiers (primitives → presets → project tokens) work. Start here. |
| `PRIMITIVES.md` | Every approved value in tables, with the recommended default for each. |
| `TASTE.md` | What we like: reference sites (EnduroSat is primary), house taste, motion ambition tiers. |
| `KICKOFF.md` | The structural questions asked when starting each client design system, with defaults. |
| `BRIEF-TEMPLATE.md` | The per-client brief: brand, direction, sitemap, kickoff answers, decisions log. |
| `COMPONENTS.md` | The standard component set: anatomy, variants, states, how each is built in Elementor. |
| `PAGE-STRUCTURES.md` | Default sitemaps and section order for brochure, lead-gen, WooCommerce, booking, portfolio, content sites. |
| `ELEMENTOR-MAPPING.md` | Where every token goes in Elementor Site Settings. |
| `CHECKLIST.md` | Accessibility (WCAG 2.2 AA), performance, SEO, legal and launch checks. |
| `tokens.css` | Primitives, presets and project tokens as CSS custom properties. |
| `components.css` | Component anatomy, reading project tokens only. |

## Using it on a project

1. Fill `BRIEF-TEMPLATE.md` with the client.
2. Answer `KICKOFF.md` (or accept the defaults).
3. Write the client's `brand.css`: project-token overrides + brand layer.
4. Load `tokens.css` → `brand.css` → `components.css`, and set the preset attributes on `<html>`:
   ```html
   <html data-density="balanced" data-type-scale="standard" data-body-size="16" data-radius="soft" data-elevation="subtle">
   ```
5. Design from `PAGE-STRUCTURES.md` and `COMPONENTS.md`; check against `CHECKLIST.md`.

Any rule can be overridden for a project when there's a reason — override it in the project, record it in the brief's Decisions log, and leave the baseline unchanged.
