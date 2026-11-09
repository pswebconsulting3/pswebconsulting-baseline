# Components

The standard component set for every site. Anatomy and states are fixed; appearance comes from project tokens. CSS classes are in `components.css`.

**Elementor column:** *Native* = rebuild with Elementor widgets so the client can edit. *HTML* = paste the generated markup into an HTML widget (motion-heavy or custom). *Theme* = template in Theme Builder.

---

## Global

| Component | Class | Anatomy | States / variants | Elementor |
|---|---|---|---|---|
| Skip link | `.hb-skip-link` | Link to `#main` | Hidden until focused | Theme |
| Container | `.hb-container` | Max width = content width + gutters | `--narrow` 720 · `--wide` 1440 · `--full` | Native (container width) |
| Section | `.hb-section` | Vertical padding from density | `--tight` · `--loose` · `--surface` · `--inverse` · `--same-bg` | Native |
| Section header | `.hb-section-header` | Eyebrow (optional) · heading · intro | Left (default) · `--center` | Native |
| Grid | `.hb-grid--2/3/4` | Columns + density gap | `--4-compact` · `--6-compact` for small items | Native (container grid) |
| Split | `.hb-split` | Media + text | `--60-40` · `--40-60` · `--reverse` | Native |

## Header and navigation

| Component | Class | Anatomy | States / variants | Elementor |
|---|---|---|---|---|
| Header | `.hb-header` | Logo · nav · actions (CTA, cart, search) | Sticky (default) · `--condensed` on scroll (shadow only) · `--overlay` transparent over hero | Theme |
| Nav link | `.hb-nav__link` | Label · underline | Hover underline grows from left · `aria-current` keeps underline | Theme (Nav Menu) |
| Dropdown | `.hb-nav__dropdown` | Panel of links | Opens on hover and focus-within | Theme |
| Mobile menu | `.hb-mobile-menu` | Toggle button · full-screen panel · 56px links · CTA | Closed / open; focus trapped while open; Esc closes | Theme |
| Breadcrumbs | `.hb-breadcrumbs` | Ordered list, `/` separators | Current page not linked | Native / Yoast |

## Footer

| Component | Class | Anatomy | Variants | Elementor |
|---|---|---|---|---|
| Footer | `.hb-footer` | Brand column (logo, line, socials) · 3 link columns · bottom bar (©, legal links) | Inverse (default) · surface | Theme |

Footer always includes: contact details or link, legal pages (privacy, cookies, terms), copyright.

## Hero

One per page. Holds the page's orchestrated moment.

| Variant | Class | Anatomy | When |
|---|---|---|---|
| Split | `.hb-hero--split` | Text column (eyebrow, H1, lead, 1–2 CTAs) · media 4:5 | Default for service businesses |
| Full-bleed image | `.hb-hero--image` | Background image · protection gradient · text bottom-left | Strong photography |
| Minimal | `.hb-hero--minimal` | H1 + lead, no media | Inner pages, text-led brands |
| Centered | `.hb-hero--centered` | Centered text, optional media below | Sparingly — not with centered sections below it |

Rules: one primary CTA, max one secondary. H1 states what the business does, not a slogan alone. Hero image gets `fetchpriority="high"`, never lazy.
Elementor: HTML widget when it carries the orchestrated motion; Native otherwise.

## Buttons

| Variant | Class | Use |
|---|---|---|
| Primary | `.hb-btn--primary` | The one main action per section |
| Secondary | `.hb-btn--secondary` | Alternative action |
| Ghost | `.hb-btn--ghost` | Tertiary, toolbar |
| Link | `.hb-btn--link` | Inline text action |
| On inverse | `.hb-btn--on-inverse` | Primary on dark bands |

Sizes `--sm` 40 · md 48 · `--lg` 56. `--icon` square. `--block-mobile` full width on mobile.
States: default · hover (bg darkens / border strengthens) · focus (ring) · active (1px down) · disabled (50% opacity) · loading (`aria-busy`, label kept).
Elementor: Native (Site Settings → Buttons).

## Cards

| Variant | Class | Anatomy | Elementor |
|---|---|---|---|
| Base | `.hb-card` | Media (optional) · meta · title · body · footer | Native |
| Surface | `.hb-card--surface` | Same, filled, no border | Native |
| Interactive | `.hb-card--interactive` + `.hb-card__link` | Whole card clickable via stretched title link; lifts 4px, image zooms 3% | Native / Loop Grid |
| Blog | `.hb-card--blog` | Image 3:2 · category · date · title · excerpt (2–3 lines) · read link | Loop Grid |
| Feature | `.hb-card__icon` | Icon 32 · title · text | Native — only for genuinely parallel features |
| Team | `.hb-card--team` | Portrait 4:5 · name · role · optional link | Native |
| Product (Woo) | `.hb-product-card` | Image 1:1 · badge (sale/new) · title · price (with sale) · add to cart | Woo Products / Loop Grid |

## Social proof

| Component | Class | Anatomy | Elementor |
|---|---|---|---|
| Testimonial | `.hb-testimonial` | Quote · rating (optional) · avatar · name · role/company | Native |
| Testimonial — large | `.hb-testimonial--large` | Single featured quote at H3 size | Native |
| Logo strip | `.hb-logos` | 6 → 3 → 2 greyscale logos, full colour on hover | Native |
| Stats | `.hb-stat` | Number (H1 size, tabular) · label | Native |

Testimonials use real names and roles. No invented quotes in client-facing designs.

## Conversion

| Component | Class | Anatomy | Elementor |
|---|---|---|---|
| CTA band | `.hb-cta` | Heading · optional text · 1–2 buttons | Native |
| CTA boxed | `.hb-cta--boxed` | Same, inside an inverse panel | Native |
| Pricing | `.hb-pricing` | Plan name · price · period · features · CTA | Native (Price Table) |
| Pricing — featured | `.hb-pricing--featured` | 2px primary border + badge | Native |

## Content

| Component | Class | Anatomy | Elementor |
|---|---|---|---|
| FAQ | `.hb-faq` | Native `<details>`: question (64px row) · answer | Native (Accordion) — add FAQ schema |
| Tabs | `.hb-tabs` | Tab list · panels; arrow-key navigation | Native |
| Prose | `.hb-prose` | WordPress editor content: headings, lists, quotes, images, captions | Theme (Post Content) |
| Media | `.hb-media--16-9` etc. | Fixed-ratio image/video frame | Native |
| Pagination | `.hb-pagination` | Prev · numbers · next, 44px targets | Loop Grid |

## Forms

| Component | Class | Anatomy | Elementor |
|---|---|---|---|
| Form | `.hb-form` | Fields 24px apart · submit · message | Native (Form) |
| Row | `.hb-form__row` | Two fields side by side, stacked on mobile | Native (column width) |
| Field | `.hb-field` | Label (optional marker) · control · hint · error | Native |
| Input / select / textarea | `.hb-input` `.hb-select` `.hb-textarea` | 48px, 16px text | Native |
| Checkbox / radio | `.hb-check` | 20px control · label, 44px row | Native |
| Form message | `.hb-form-message` | Success: what happens next. Error: what to fix | Native |

States: default · hover · focus · invalid (`aria-invalid` + error text) · disabled.
Rules: labels always visible (no placeholder-only labels). Mark optional fields, not required ones, when most are required. Spam protection on every form (honeypot or Turnstile/reCAPTCHA).

## Feedback and overlays

| Component | Class | Anatomy | Elementor |
|---|---|---|---|
| Badge | `.hb-badge` | Short label | Native |
| Notice | `.hb-notice--info/success/warning/error` | Icon · text | Native |
| Modal | `.hb-modal` | Native `<dialog>`: title · content · actions · close | Popup |
| Cookie banner | `.hb-cookie` | Text · accept · reject · settings (equal prominence for accept/reject) | Plugin (Complianz / CookieYes), styled |

## WooCommerce

| Component | Class | Anatomy | Elementor |
|---|---|---|---|
| Cart | `.hb-cart` | Line items (thumb · name/variant · qty · price · remove) + sticky summary (subtotal · shipping · total · checkout) | Woo Cart widget, styled |
| Quantity | `.hb-qty` | − · input · +, 44px buttons | Woo |
| Mini-cart | `.hb-mini-cart` | Slide-in panel from right | Woo Menu Cart |

Also style (from Woo defaults): single product (gallery · title · price · variations · add to cart · tabs), checkout (single column on mobile, express pay first), my-account, order received.

## Templates

| Template | Contents |
|---|---|
| 404 | Short message · search · links to key pages · CTA |
| Search results | Query · count · result cards · empty state |
| Blog archive | Hero minimal · category filter · 3-up blog cards · pagination |
| Single post | Breadcrumbs · title · meta · featured image 16:9 · prose · author · related posts · CTA |
| Legal page | Minimal hero · narrow container · prose |
