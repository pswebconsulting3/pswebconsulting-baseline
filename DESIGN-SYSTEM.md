# House Baseline Design System

The standing rules for every website PS Web Consulting produces. Every project is built on this baseline, so nobody has to re-explain the fundamentals at the start of a job. Any rule can be overridden in a project when there's a reason — the override lives in the project, never here.

---

## 0. How it works — three tiers

| Tier | What | Who decides | Where |
|---|---|---|---|
| **Primitives** | Every approved raw value: spacing, sizes, widths, radii, shadows, ratios, motion | Baseline (fixed) | `tokens.css` §1, `PRIMITIVES.md` |
| **Presets** | Ready-made bundles: radius, density, type scale, body size, elevation | Project picks one of each | `tokens.css` §2 |
| **Project tokens** | The names components read (`--content-width`, `--radius-card`, `--section-y`…) | Defaults here; overridden at kickoff | `tokens.css` §3, client `brand.css` |

Components only ever read project tokens. Change a project token and every component follows.

**Fixed on every project:** the primitive tables, motion physics, component anatomy, accessibility and quality checklist, never-do list.
**Chosen per project (`KICKOFF.md`):** content width, breakpoint set, density, type scale, body size, radius, elevation, header size, image ratios.
**Brand, per project (`BRIEF-TEMPLATE.md`):** logo, colours, fonts, imagery style, icon set, copy and tone, signature element, sitemap, features.

If a design still shows a placeholder from the brand layer, it is not ready to show a client.

---

## 1. Spacing

- Every gap, padding and margin comes from the `--space-*` primitives (4px base, 8px rhythm). No arbitrary values.
- Section padding comes from the density preset — never hand-set per section.
- Related things sit close, unrelated things far apart. One step or three, never one-and-a-half.
- Use the fixed in-section rhythm (eyebrow → heading 12, heading → text 16, text → buttons 32). See `PRIMITIVES.md` §1.
- Prefer flex/grid `gap` over margins on children.

## 2. Layout

- **Desktop-first, Elementor breakpoints** (tablet ≤1024, mobile ≤767), so CSS and the Elementor editor agree. Each per-device token has a desktop, tablet and mobile value.
- Mobile is designed, not shrunk: its own section padding, its own type sizes, stacked layouts, full-width CTAs where it helps.
- Card grids use the column-count classes; gaps and collapse follow `PRIMITIVES.md` §2.
- Don't center everything. A page of centered heading + centered paragraph + centered button is the default AI layout. Vary alignment and column split with a reason each time.
- Body text never runs wider than 68ch. Headings cap at 22ch.
- No horizontal scroll at any width from 320px to 1920px.

## 3. Typography

- Sizes come from the type-scale preset; every heading level H1–H6 has a desktop, tablet and mobile size.
- Body 16px minimum. Form inputs 16px minimum.
- One `h1` per page. Never skip heading levels for looks — style a lower level instead.
- Up to two families. One family for everything is allowed. Mono only for data or code.
- Max four weights loaded in total.
- Headings `text-wrap: balance`, paragraphs `text-wrap: pretty`.
- Line height tightens as size grows: 1.1 for display, 1.6 for body.

## 4. Shape and surface

- One radius preset per project, held throughout. Exceptions (a pill badge in a sharp site) are deliberate and rare.
- Nested corners: inner radius = outer radius − the padding between them.
- Shadows are a state signal (hover, scrolled header, floating layer), not decoration. A resting card can have a border instead.
- Shadows are tinted with the darkest brand neutral, never pure black.
- No glassmorphism or blur panels by default. The only gradient allowed by default is a protection gradient behind text on photos.

## 5. Colour structure

Colours are per client, but every palette fills the same roles so components and Elementor Global Colors always work:

- Primary + on-primary · Secondary + on-secondary · Accent
- Background · Surface · Surface-alt · Inverse + on-inverse
- Text · Text-muted · Border · Border-strong
- Success · Warning · Error · Info — derived from the palette, not generic red/green/amber

Rules:
- Hover colour = primary darkened ~12% unless the brand defines one.
- Every text/background pair passes WCAG AA (4.5:1 body, 3:1 large text and UI borders). Test on-primary, muted text and inverse sections specifically.
- Colour is never the only signal (errors get text, links get underline).
- Max two background colours per page plus one inverse band.

## 6. Motion

Motion is where our sites earn their fee, and where they most easily go wrong.

- **Physics.** Durations from `--dur-*`, easings from `--ease-*`. Nothing bespoke typed inline.
- **Duration by distance.** Hover `--dur-fast`; entrance `--dur-slow`; hero `--dur-slower`/`--dur-page`. A 500ms hover feels broken; a 180ms reveal is invisible.
- **One orchestrated moment per page.** Usually the hero: four or five things arriving in a deliberate order, staggered by `--stagger-base`. Below the fold stays quiet.
- **Small reveals.** 24px, 40px max.
- **Transform and opacity only.** Never animate top, left, width, height or margin.
- **Reduced motion is not optional.** The media query ships on every project and gets tested. Content is never left invisible if JS fails.
- **Library.** GSAP + ScrollTrigger for orchestrated and scroll-driven work. CSS transitions for hover, focus and state. Lenis only when smooth scroll is a stated part of the direction. Never Elementor Motion Effects and GSAP on the same element.

## 7. Components

The standard set and its anatomy is in `COMPONENTS.md`, styled in `components.css`. Build from it before inventing anything. Default page structures per site type are in `PAGE-STRUCTURES.md`.

## 8. Copy conventions

- Sentence case for buttons, labels, headings and nav.
- Active voice. A control names what happens: "Send message", not "Submit". "Book a consultation", not "Learn more".
- An action keeps its word through the flow: "Publish" → "Published".
- Name things the way the client's customers do, not the way the CMS does.
- Errors say what went wrong and how to fix it. Empty states say what to do next.
- Real copy from the brief — never lorem ipsum in anything shown to a client.

## 9. Never do

These exist because every AI design tool converges on the same look.

- Cream background + serif display + terracotta accent
- Near-black background + one acid-green accent
- Blue-to-purple gradients, gradient-blob heroes
- Glassmorphism cards everywhere
- Cards with a coloured left border as the only accent
- Emoji as icons
- Numbered 01 / 02 / 03 markers on content that isn't a sequence
- Icon + heading + two lines feature grids on content that isn't three parallel features
- Every section centered
- Stock-photo handshake / laptop clichés when the client has real photography
- Thirty independent scroll fades instead of one orchestrated moment
- "Learn more" as the only CTA text on the page

And always:
- One deliberate aesthetic risk per project, and we can say what it is and why.
- **One signature element** drawn from the client's world — their material, process or vernacular. Named in the brief before building. Everything else stays disciplined so it has room to land.

## 10. Quality floor

Every project ships with the full `CHECKLIST.md` passed. Not negotiable per project.

## 11. Per-project setup

```
client-name/
  01-brief/design-brief.md   — from BRIEF-TEMPLATE.md + KICKOFF.md answers
  02-brand-assets/           — logo (SVG), brand guide, fonts
  brand.css                  — project tokens + brand layer, filled in
  references/                — 3–5 screenshots, with what to take from each
  content/                   — real copy, product names, numbers
```

Never brief with adjectives alone. "Modern and clean" produces the default.

## 12. WordPress / Elementor handoff

See `ELEMENTOR-MAPPING.md` for exactly where every token goes. Decide the build path at the start, not at handoff:

- **Custom theme** (preferred for motion-heavy sites): hand the approved design to Claude Code and build a theme on `tokens.css` + `components.css`.
- **Elementor**: tokens go into Site Settings; standard sections are rebuilt natively so the client can edit them; orchestrated hero and scroll-driven work go in as HTML widgets.
- **Changes to an existing site**: capture the current page first (screenshot + URL) so the new section inherits the site's existing rhythm.
