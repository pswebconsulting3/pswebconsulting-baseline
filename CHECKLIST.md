# Quality checklist

Ships on every project. Run before showing a client a design and again before launch. Every box must be ticked or have a written reason in the Decisions log.

---

## Design (before client presentation)

- [ ] Only project tokens used; no off-scale spacing or sizes
- [ ] No brand-layer placeholder values left
- [ ] Section padding consistent with the density preset
- [ ] One `h1`; heading levels in order
- [ ] One primary CTA visible above the fold on desktop and mobile
- [ ] Mobile designed (stacking, CTA, type sizes), not just shrunk
- [ ] Never-do list checked (`DESIGN-SYSTEM.md` §9)
- [ ] Signature element present and named
- [ ] Real copy, no lorem ipsum, no invented testimonials
- [ ] Buildable in Elementor; anything needing custom code flagged

## Accessibility — WCAG 2.2 AA

- [ ] Text contrast 4.5:1 (body), 3:1 (≥24px or ≥19px bold), 3:1 for UI borders and icons
- [ ] Colour never the only signal (links underlined in body copy; errors have text)
- [ ] Visible focus on every interactive element
- [ ] Focus not hidden behind the sticky header or cookie banner (2.4.11)
- [ ] Keyboard: everything reachable and operable; logical tab order; no traps; Esc closes menus and modals
- [ ] Skip link to main content
- [ ] Landmarks: header, nav, main, footer
- [ ] Touch targets ≥ 44 × 44px (WCAG floor is 24px; house floor is 44)
- [ ] Works at 200% zoom and at 320px width without horizontal scroll
- [ ] Every form field has a visible label; errors explain the fix and are announced
- [ ] Alt text on content images; empty alt on decorative ones
- [ ] Video has captions; no autoplay with sound; anything moving > 5s can be paused
- [ ] `prefers-reduced-motion` honoured and tested
- [ ] `lang` attribute set; page titles unique and descriptive
- [ ] Higher level if the client is public sector or regulated

## Performance

- [ ] LCP < 2.5s, CLS < 0.1, INP < 200ms on mobile (PageSpeed Insights, field data where available)
- [ ] Hero image: correct size, WebP/AVIF, `fetchpriority="high"`, not lazy
- [ ] Other images lazy, sized (width/height or aspect-ratio), within `PRIMITIVES.md` §8 budgets
- [ ] Fonts: self-hosted WOFF2, max 2 families / 4 weights, `font-display: swap`, heading font preloaded
- [ ] Only GSAP loaded for motion (plus Lenis if chosen); no unused libraries
- [ ] Elementor performance features on; unused icon fonts disabled
- [ ] Caching and image optimisation plugin configured
- [ ] Third-party scripts audited (chat, analytics, pixels) and deferred

## SEO

- [ ] Unique title (≤ 60 chars) and meta description (≤ 155) per page
- [ ] One `h1` per page containing the page's main topic
- [ ] Clean URLs; redirects mapped from the old site
- [ ] XML sitemap submitted; robots.txt correct; staging set to noindex, live set to index
- [ ] Open Graph image and tags
- [ ] Schema: Organization / LocalBusiness, FAQ, Product (Woo), BreadcrumbList, Article
- [ ] Image file names and alt text descriptive
- [ ] Internal links between related services and posts
- [ ] Google Search Console and Analytics (GA4) connected

## Content and forms

- [ ] Every page has one job, written in the brief
- [ ] CTA wording consistent across the site
- [ ] Phone numbers and emails clickable
- [ ] Forms: spam protection, success message says what happens next, notification email tested, submissions stored
- [ ] Empty states (no search results, empty cart) say what to do next
- [ ] 404 page helpful

## Legal and privacy (UK/EU)

- [ ] Privacy policy, cookie policy, terms (if selling)
- [ ] Cookie banner: accept and reject equally prominent; no non-essential cookies before consent
- [ ] Form consent wording where marketing is involved
- [ ] Company details in footer where legally required

## WooCommerce (if applicable)

- [ ] Test orders end-to-end for each payment method
- [ ] Shipping zones and tax correct
- [ ] Transactional emails branded and tested
- [ ] Stock, sale prices and variations display correctly
- [ ] Checkout works as guest on mobile

## Launch

- [ ] Tested on real devices: iPhone Safari, Android Chrome, desktop Chrome, Safari, Firefox, Edge
- [ ] Tested at 320, 375, 768, 1024, 1280, 1440, 1920
- [ ] Favicon and app icons
- [ ] SSL; www/non-www and http redirects
- [ ] Backups and uptime monitoring
- [ ] Client handover: editing guide, logins, what not to touch
