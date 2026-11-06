# House Baseline Design System

The standing rules for every website this agency produces. Structure is fixed here. Brand is not.

Two layers:

- **Structure layer** — spacing, scale, motion, layout, quality floor. Identical on every project. Defined in `tokens.css` and `components.css`.
- **Brand layer** — palette, typefaces, radius personality, signature element. Empty in this baseline. Filled per project from the client's own material.

If a design shows a placeholder value from the brand layer, it is not ready to show a client.

---

## 1. Spacing

Base unit is 4px. Rhythm is 8px. Every gap, padding and margin comes from the `--space-*` scale in `tokens.css`. No arbitrary pixel values.

Section spacing uses `--section-y`, which is fluid. Mobile does not get desktop padding scaled down; it gets its own value from the same clamp.

Related things sit close, unrelated things sit far apart. If two elements are 16px apart and two others are 20px apart, the reader learns nothing from the difference. Use one step or three steps, never one-and-a-half.

## 2. Type

Three roles, always: **display**, **body**, **utility/mono**. Display and body are different families, chosen for this client for a stated reason. Never one family doing all three jobs.

Sizes come from the `--text-*` scale. It is fluid, so there are no separate mobile font sizes to maintain.

Line length is capped: `--measure-prose` (68ch) for body copy, `--measure-heading` (22ch) for display. Full-width paragraphs across a 1280px container are a defect.

Headings use `text-wrap: balance`. Paragraphs use `text-wrap: pretty`.

## 3. Layout

Mobile-first. Base styles target the smallest screen, `min-width` queries add upward. Breakpoints: 480 / 768 / 1024 / 1280 / 1536.

Twelve-column grid. Content container 1280px, reading container 720px, wide container 1536px.

Do not center everything. A page where every section is a centered heading, centered paragraph and centered button is the default AI layout. Vary the alignment and the column split section to section, with a reason each time.

## 4. Radius personality

Pick one per project and hold it: **sharp** (`--radius-none`), **soft** (`--radius-md`/`lg`), or **pill** (`--radius-full`). Mixing all three reads as indecision. Small exceptions are fine — a pill-shaped tag inside a sharp-cornered card — but they are exceptions, not a fourth option.

## 5. Motion

Motion is where our sites earn their fee, and where they most easily go wrong.

**Physics.** All durations come from `--dur-*`, all easings from `--ease-*`. Nothing gets a bespoke `cubic-bezier` or a `0.3s` typed inline.

**Duration by distance.** Small state change, `--dur-fast`. Element entering the viewport, `--dur-slow`. Large transform or an orchestrated hero, `--dur-slower` or `--dur-page`. A 500ms hover feels broken; a 180ms scroll reveal is invisible.

**One orchestrated moment per page.** Usually the hero. A sequence where four or five things arrive in a deliberate order, staggered by `--stagger-base`, lands far harder than thirty independent elements each fading in as you scroll. Everything below the fold should be quiet by comparison.

**Reveal distance is small.** 24px, 40px at most. Elements sliding 100px into place look like a template.

**Never animate `top`, `left`, `width`, `height`, or `margin`.** Only `transform` and `opacity`. Anything else costs frames on the mid-range Android phones half the traffic arrives on.

**Reduced motion is not optional.** The media query in `tokens.css` ships on every project. Test it.

**Library standard.** GSAP with ScrollTrigger for orchestrated and scroll-driven work. Native CSS transitions for hover, focus and simple state. Lenis only when smooth scroll is a deliberate part of the direction, never as a default. Do not stack three animation libraries on one site.

## 6. Quality floor

Every project ships with all of these. They are not deliverables to negotiate.

- Responsive from 320px to 1920px with no horizontal scroll at any width
- Visible keyboard focus on every interactive element
- Text contrast meets WCAG AA: 4.5:1 body, 3:1 for large text and UI borders
- Touch targets at least 44px
- `prefers-reduced-motion` honoured
- Real alt text on content images, empty alt on decorative ones
- One `h1` per page, heading levels never skipped
- Form errors say what went wrong and how to fix it
- Empty states say what to do next
- Images sized and lazy-loaded below the fold, `fetchpriority="high"` on the hero image

## 7. Copy conventions

Sentence case for buttons and labels. Active voice. A control names what happens: "Send message", not "Submit".

An action keeps the same word through the whole flow. The button that says "Publish" produces a message that says "Published".

Name things the way the client's customers name them, not the way the CMS does.

## 8. Anti-generic rules

These exist because the default output of any AI design tool converges on the same look.

- No cream background with a serif display and a terracotta accent
- No near-black background with one acid-green accent
- Numbered markers (01 / 02 / 03) only when the content is genuinely a sequence
- No gradient-blob hero
- Icon-plus-heading-plus-two-lines feature grids only when the content really is three parallel features
- Every project takes one deliberate aesthetic risk, and we can say what it is and why

**Signature element.** Each site has one thing it is remembered by, derived from the client's actual world — their material, their process, their vernacular. Everything else stays disciplined so the signature has room to land. Name it in the project brief before building.

## 9. Per-project setup

For each new client, create a small brand source and attach it to the Claude Design project alongside this baseline:

```
client-name/
  brand.css        — the BRAND LAYER block from tokens.css, filled in
  BRIEF.md         — goal, audience, single job of each page, signature element,
                     radius personality, motion direction, one aesthetic risk
  references/      — 3-5 screenshots of sites with the intended feel
  content/         — real copy, real product names, real numbers
```

Never brief with adjectives alone. "Modern and clean" produces the default. Reference images plus real content produce something specific.

## 10. WordPress / Elementor handoff

Output from Claude Design is HTML, CSS and JS. There is no Elementor import format. Decide the path at the start of the project, not at handoff.

**New builds.** Prefer handing the approved design to Claude Code and building a proper theme. Animation quality and performance are both materially better than anything reproducible in the Elementor editor.

**Elementor builds.** Treat the output as a visual spec plus a source of real code:
- Load `tokens.css` and `components.css` through the child theme, not the Elementor Custom CSS box
- Map the token values into Elementor's Global Colors and Global Fonts so editor controls stay usable for the client
- Hero sections, orchestrated sequences and any scroll-driven work go in as HTML widgets with the generated markup
- Standard content sections get rebuilt natively so the client can still edit them
- Do not use Elementor Motion Effects alongside GSAP on the same element

**Existing site changes.** Capture the current page first (screenshot plus the live URL) and attach it, so the new section inherits the site's existing rhythm rather than importing a different spacing scale into one page.
