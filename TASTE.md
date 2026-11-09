# Taste & References

What PS Web Consulting likes. Read this before designing any client site, after `DESIGN-SYSTEM.md`. The baseline sets the **rules**. This file sets the **ambition**: how far past the rules to go, and in which direction.

Brand stays per client. Never copy a reference's colours, fonts, logo, copy or signature effect. Take the *technique* and the *standard*, then apply it to the client's own world.

---

## 1. Primary reference

**EnduroSat — Space Service** · https://www.endurosat.com/space-service/

> **This is the primary reference project.** When in doubt about pacing, motion, hierarchy or how far to push, ask "what would this page do?"

Why it's the benchmark:
- **The page is an explanation, not a brochure.** It goes problem → solution → "your mission in two steps" → how each step works → proof → CTA. Each scroll stage answers one question.
- **Scroll-told process.** The two-step story (Define → Receive) is pinned and walked through stage by stage. A "Scroll to continue" cue tells the user the page is driving.
- **Interactive explainers instead of paragraphs.** Selectable applications (remote sensing / connectivity), live-looking telemetry values, an animated cost comparison (traditional vs. them, USD/GB), a 0 → 6 months timeline.
- **3D product and video as proof.** The satellite is shown, not described.
- **Big counted numbers for credibility** (100 satellites, 500 TB, 900 years) — counted only because they're real proof, never decoration.
- **Mega-menu with product imagery and specs** in the header.
- **Built on WordPress.** Proof that this level of experience fits our stack.

## 2. What we're consistently drawn to

These patterns run through the whole list. Treat them as house taste.

1. **Motion is the experience, not decoration.** Animation explains, sequences and reveals. If removing it loses no meaning, it shouldn't be there.
2. **Step-by-step storytelling.** Complex offers get explained one stage at a time, with pinned sections, scroll-scrubbed progress and numbered stages *only when it's a real sequence* (Noomo Labs, EnduroSat, Polpharma's 1 → 4 lifecycle).
3. **Depth: 3D objects and layered space.** A hero object you can see from several angles, built in WebGL or from rendered frames or video (Persepolis, Polpharma, EnduroSat, Noomo).
4. **Rich, living backgrounds.** Soft animated gradients, shader fields and light, with colour used as atmosphere rather than flat fills (Jasmina Denner, Ivapix).
5. **Video as a material.** Looping, muted, art-directed clips, often scrubbed by scroll rather than just played (Polpharma's hero has a separate vertical cut for mobile; Aengel; Nota).
6. **Editorial, confident typography.** Huge display type with tight leading, split into lines or words for animation, alongside small uppercase labels for hierarchy (Lando Norris, Aengel, Nota, Sobha).
7. **A product that travels with the scroll.** One hero object stays on screen and transforms as the story moves on (Agrumea, Polpharma's bottle, BMW F3).
8. **Strong, clear hierarchy despite the effects.** Even the wildest pages have an obvious reading order: eyebrow label → headline → one line → CTA.
9. **Designed headers.** Minimal at rest, then they open into rich menus with imagery (Lando Norris's image menu, EnduroSat's product mega-menu, Polpharma).
10. **Responsiveness treated as a separate design.** Mobile gets its own composition and its own media, not a squashed desktop (Lando Norris, Polpharma).
11. **Sound, optional and opt-in.** Used only for immersive experiences, always off by default with a visible toggle (Noomo Labs: "To make this experience more immersive we use sound effects", with an on/off waves toggle).

## 3. Reference library

| # | Site | What to take |
|---|---|---|
| ★ | [EnduroSat — Space Service](https://www.endurosat.com/space-service/) | **Primary.** Everything: scroll-told explanation, 3D, video, interactive explainers, pacing, mega-menu. |
| 1 | [Jasmina Denner](https://jasminadenner.com/) | Simplicity with richness: animated gradient backgrounds, colour theory, calm but constant motion. Personal brand done premium. (Built by Noomo.) |
| 2 | [Ivapix](https://ivapix.cloud/) | Colour, background effects, clear hierarchy, animations, header. |
| 3 | [AWSMD](https://awsmd.com/) | Animation craft: transitions, reveals, hover behaviour. |
| 4 | [Noomo Agency](https://noomoagency.com/) | The whole concept treated as one experience, plus the motion language. |
| 5 | [Noomo Labs](https://labs.noomoagency.com/) | **Top of the list for immersion.** Loader → "Immerse me" entry, opt-in sound, 3D, a customisable scene, and everything explained step by step. |
| 6 | [Noomo Beat](https://beat.noomoagency.com/) | Audio-reactive effects: visuals driven by music. |
| 7 | All Noomo projects | Consistent motion vocabulary across very different brands. Study how one team's motion system flexes. |
| 8 | [Lando Norris](https://landonorris.com/) | Effects, motion, colour, editorial typography, responsiveness. Image-led menu, horizontal photo story, hover image swaps (helmet base → hover), animated illustrations, signature as a graphic. |
| 9 | [Persepolis Reimagined (Getty)](https://persepolis.getty.edu/) | 3D environments and storytelling inside a reconstructed space. |
| 10 | [Polpharma Biologics](https://www.polpharmabiologics.com/) | Effects, colour, header, 3D, hierarchy. A scroll-scrubbed hero video (separate mobile cut), a 3D product, a numbered lifecycle, a calm palette in a serious sector. (By Widelab.) |
| 11 | [BMW F3](https://www.bmwf3.com/) | Product animation and scroll-driven reveals. |
| 12 | [Aengel — Contact](https://aengel.io/contact) | Everything: motion, video, typography, colour. Proof that even a contact page can be a moment. |
| 13 | [Agrumea Farm](https://www.agrumeafarm.it/en) | A hero product that stays on screen and changes as you scroll. |
| 14 | [Sobha Privy Collection](https://sobha-privy-collection.com/) | Effects, motion, luxury typography, cinematic image reveals. |
| 15 | [Nota (Uprock)](https://nota.uprock.pro/) | Effects, typography, video. |

## 3b. Read from the page source

What the fetched markup shows. Each line is backed by a real trace in the page (duplicated labels, loaders, media files). Persepolis and BMW F3 render entirely in JavaScript, so their source shows nothing. Nota blocks automated access, so its notes rely on the brief only.

| Site | Built with | Evidence in the markup → technique |
|---|---|---|
| EnduroSat | WordPress | Nav labels written 2–3× → **text-roll hover**. A "Drag" label → **custom cursor with a label**. "Scroll to continue" → **pinned chapter**. 0 → 6 months timeline, USD/GB comparison → **animated data explainers**. Product mega-menu with images and specs. External mission configurator as the main CTA. |
| Ivapix | WordPress | **Interactive slider explainer** (drag "Pixies" to add storage / PHP workers, with a matching image per item). **Tabbed feature explainer** (9 features, each with a screenshot). A spec list used as the offer. Mega-menu with a featured image card. |
| AWSMD | Next.js | Hero video. One italic letter in the headline ("*A*wesome") → **typographic accent**. Repeated phrase → **infinite marquee**. Stat cards each with a **looping 3D-object video**. Images set inside a headline ("Data ![texture] Science") → **inline media in type**. Buttons labelled twice → text-roll hover. Logo marquee. |
| Noomo Agency | Custom | Preloader logo. Two logo images → **logo swap / animated mark**. All-caps statement hero. Client list as a ticker. Pixel-arrow "Scroll" cue. Budget chips in the form and an animated thank-you state. |
| Noomo Labs | Custom, WebGL | Loader with a **0–100% counter**. **Opt-in sound** with a waves on/off toggle. "Customize me" scene controls (patterns, values, restart). "Immerse me" **entry gate**. Bracketed nav `[Work]`. |
| Jasmina Denner | Custom (by Noomo) | Role switcher (engineer / investor / scientist…) with arrows → **rotating identity carousel**. Card list of four work areas. Values list. "Back to top". |
| Lando Norris | Webflow + Rive | "Load Norris" → **branded loader**. Rive placeholders → **Rive vector animation**. Paired base/hover images on each helmet → **hover image swap**. Captioned photo sequence → **horizontal scroll gallery**. "Please rotate your device" and "tap to lock" → **mobile handled as its own mode**. Image-led menu. |
| Polpharma | Webflow + Unicorn Studio (by Widelab) | **Separate desktop and vertical-mobile scrub videos** for the hero. A transparent `.webm` device video. Bottle image repeated in layers → **layered product reveal**. Lifecycle 1 → 4.3 as a real sequence. Team row duplicated → infinite carousel. Insight dates stacked as DD / MM / YYYY. |
| Aengel | Next.js, Three.js / WebGPU | "Fetching assets" loader and "Enter in the experience" gate. **A LITE VERSION link → a lightweight fallback site**. "Drag to switch project" → **draggable project slider**. Short lines revealed in turn as you scroll ("I write lines of code that tell a story…"). "Email copied" → **copy-to-clipboard feedback**. |
| Noomo Beat | Custom, WebGL + Soundraw AI | **5-question quiz (01/05 → 05/05)** builds a personal result (genre, mood, tempo, theme, colour), with a "random selection" shortcut. Loader copy ("generating music… scene… emotions") → **narrated loading**. 3D scene with focus/move controls. **Shareable result** (choose an album cover, copy link, socials). A friendly error state with Regenerate. |
| Sobha Privy Collection | Custom (by Vide Infra) | **Menu as numbered chapters** (Chapter 1 About → 6 The idea). Long line-broken statements revealed line by line. Asymmetric image clusters (small / large / small) → **editorial collage reveals**. Tabs for the "three worlds" (Mansions / Villas / Penthouses). Tenets carousel with video. Location list counted 1 — 4 next to a map, plus a separate **3D map page**. Separate @xs images for mobile and a rotate-device prompt. Closing statement repeated → **marquee or masked text**. |
| Agrumea | Prismic + custom | Loader 0%. Rotating circular text badge ("Scroll to discover"). **10 products in a scroll-driven hero carousel**. Menu letters doubled ("mmeennuu") → **per-letter hover stagger**. IT / EN switch. |

**What the source shows recurring across these sites** (treat as house vocabulary):
- **Text-roll hover** on nav and buttons (label duplicated, one slides out, one slides in). Seen on 4 of the 10.
- **Branded preloader with a % counter.** Only for Immersive builds with heavy assets; never on a Standard site.
- **Infinite marquees** for phrases, logos or team.
- **Custom cursor with a context label** ("Drag").
- **A separate mobile composition and media** (vertical video, rotate prompt).
- **A lightweight fallback** for heavy 3D sites (Aengel's Lite version). Required on every Immersive build.
- **Interactive explainers** (sliders, tabs, configurators, quizzes) instead of feature paragraphs.
- **Chapters.** Long pages are organised and labelled as numbered chapters, with the menu acting as a table of contents (Sobha, EnduroSat). A real sequence, so numbering is allowed.

## 4. Motion ambition tiers

The baseline's motion rules (`DESIGN-SYSTEM.md` §6) are the **Standard** tier. These references sit mostly in **Expressive** and **Immersive**. Pick the tier at kickoff (`KICKOFF.md`) and record it in the brief, alongside budget and hosting reality.

| | Standard | Expressive *(house default for new work)* | Immersive |
|---|---|---|---|
| Use for | Small brochure, tight budget, client edits everything in Elementor | Most marketing sites, lead-gen, premium brands | Flagship launches, products, campaigns, agency showcase |
| Moments | One orchestrated hero moment | Hero moment + 1–3 scroll-told chapters (pinned / scrubbed) | The page is a guided experience end to end |
| Techniques | Reveals, staggers, hover | + text-roll hover, split-text headlines, marquees, pinned process sections, scroll-scrubbed video or image sequences, travelling hero product, animated gradient backgrounds, image-menu header, interactive slider / tab explainers, cursor labels | + WebGL / 3D scenes, shaders, cursor-reactive fields, opt-in sound, % preloader and entry gate, Rive animations, **plus a required lite fallback** |
| Libraries | GSAP + ScrollTrigger, CSS | + GSAP SplitText, Lenis smooth scroll | + three.js (or Spline / Unicorn Studio embeds), Web Audio |
| Reference | — | Polpharma, Jasmina Denner, Lando Norris, Agrumea | EnduroSat, Noomo Labs, Persepolis, Beat |

Rules that hold at **every** tier:
- Durations and easings come from `--dur-*` / `--ease-*`. Scrubbed animation follows the scroll, so it has no duration.
- Animate transform and opacity only. Shader and canvas work is fine because it runs on the GPU, not by animating layout.
- `prefers-reduced-motion`: pinned chapters become static stacked sections, video shows a poster frame, 3D shows a still render, and gradients stop moving. The content stays complete.
- Content is readable with JS off or WebGL unavailable (poster images, real HTML text — never text baked into canvas or video).
- Sound is never autoplayed, and its on/off toggle is always visible.
- Performance budget from `CHECKLIST.md` still applies: lazy-load 3D and video below the fold, keep compressed video ≤ 3 MB for the hero, and serve separate mobile media.
- A mobile composition is designed, not just inherited from desktop.

## 5. How to use this file

1. At kickoff, choose the motion tier and pick **1–3 references** from §3 that fit the client's industry and offer. Note them in the brief.
2. Name what is taken from each reference (e.g. "EnduroSat's pinned two-step explainer for our 3-step onboarding"). Never just "make it like X".
3. The client's signature element (`DESIGN-SYSTEM.md` §9) is usually where the chosen tier spends its effort.
4. If a reference conflicts with a baseline rule, the tier table above decides. Log the override in the brief's Decisions log.
