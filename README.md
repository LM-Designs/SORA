# Handoff: SORA Landing Page

## Overview
Marketing landing page for SORA, a coastal brunch & aperitivo restaurant in Durrës, Albania. Sections: hero, About, Brunch marquee + gallery, Menu links (PDF), Aperitivo marquee + gallery, Footer/Contact. Responsive: desktop (≥768px, designed at 1440 and scales to 1920) and mobile (<768px, designed at 375 and scales fluidly).

## About the Design Files
The included `SORA Landing Page.dc.html` is a **design reference** built in a prototyping tool (custom template syntax, not production code). It renders correctly only inside that tool's runtime (`support.js`, `{{ }}` template holes, `<sc-if>`/`<sc-for>` custom tags). Do NOT ship this file as-is — **recreate the design** in whatever stack you choose (plain HTML/CSS/JS, React, Next.js, etc.), using the exact values documented below.

## Fidelity
High-fidelity. Colors, typography, spacing, and interactions are final — implement pixel-perfectly.

## Screens / Views

### 1. Header / Nav (sticky top, dark navy bg #041E42)
- Logo: `assets/sora-logo.svg`, centered, 169×30px desktop / 124×22px mobile.
- Nav links (desktop, both sides of logo): ABOUT, GALLERY (left) — Menu, CONTACT-turned-"MAKE A RESERVATION" (right).
- Nav link style: font Geist Mono (Menu label uses Geist), 600 weight, 12px, letter-spacing 1.5px (2px for "Menu"), color `rgba(255,255,255,0.5)` default, `#F0EDD1` active/hover.
- Mobile: hamburger icon (3 bars, 20×2px, #f0edd1) opens a dropdown with the same 4 links + reservation button below.
- "MAKE A RESERVATION" button: 1px solid `#C0E0F2` border, `#C0E0F2` text, Geist Mono 12px, letter-spacing 1px, padding 6px 12px, no border-radius. On click: `tel:+355674050776` (opens phone dialer). Hover: text turns `#F0EDD1` (same nav hover rule).

### 2. Hero
- Desktop: 800×400px arch photo (`assets/hero-arch.png` or `-sm.jpg`), border-radius 400px 400px 0 0 (top half circle), sitting on navy bg. Directly below: a matching bottom half-circle (border-radius 0 0 400px 400px), navy fill on cream `#F0EDD1` bg, containing two time labels: "08:00 / DOORS OPEN DAILY" and "18:00 / APERITIVO BEGINS" (Freehand cursive 32px for time, Geist Mono 18px uppercase 500 weight, letter-spacing 2px, color `#c0e0f2`).
- Mobile: same structure scaled to 375px canvas — top half circle 375×187.5px, bottom half circle 375×187.5px.

### 3. About section (id="about-section", bg `#F0EDD1`)
- Heading: "A COASTAL BRUNCH & APERITIVO RITUAL" — Genos 500, 96px desktop / 64px mobile, uppercase, color `#263264` (desktop) / `#041E42` (mobile), centered.
- Paragraph: "Located in Durres, Albania, where the espresso machine hums before the sun is up, brunch stretches into afternoon, and the first spritz always meets the last light on the Adriatic." — Geist Mono 500, 14px desktop / 12px mobile, color `#474747`, centered, max-width 775px desktop / 327px mobile.
- **Animation**: heading + paragraph reveal word-by-word on scroll (IntersectionObserver, fires once at 20% visibility): each word fades in (opacity 0→1) and slides up (translateY 10px→0), 0.35s ease, staggered 20ms per word.
- Photo collage: shopfront illustration SVG + 5-6 photos absolutely positioned at specific coordinates (see file for exact px), one rotated "sunrise/sunset" arch-text SVG.
- Cocktail illustration (`assets/cocktail-illustration.svg`, 122×154px desktop / 205×154px mobile) with "The ° hour" text as a flattened SVG image (`assets/the-hour.svg`, NOT live text — rotated -9.7deg) positioned over it.
- **Animation**: cocktail illustration "shakes" on scroll into view — rotates ±6° oscillating down to 0 over 2.4s ease-in-out, `transform-origin: 50% 85%`, fires once.
- Second heading: "Inspired by Taste & Time" (Genos 96px) + paragraph "A curated selection of dishes and drinks, crafted with seasonal ingredients from the Adriatic coast." (Geist Mono 14px, #474747).

### 4. Brunch marquee (bg `#f0edd1`)
- Infinite horizontal auto-scroll (CSS `@keyframes marquee-scroll`, 22s linear infinite, translateX 0 → -50%, track is doubled content for seamless loop).
- Alternates "Brunch" text (Freehand cursive 24px, color `#15316d`) and rotating icon set (`assets/brunch-icon-a/b/c/d.svg`, 44px).

### 5. Brunch gallery (id="gallery-section")
- Desktop: 4 photos in a row, fixed widths, height 497px, object-fit cover, full-bleed (no gaps).
- Mobile: same 4 photos but as a **carousel** — 2 visible at a time (187.5px each of 375px viewport), tap arrow (40px circle, `rgba(255,255,255,0.5)` bg, `#F0EDD1` stroke arrow) to slide one image at a time; track uses `transform: translateX(-N*50%)` with 0.4s ease transition. Left arrow only shows when scrolled right; right arrow hides at the end.

### 6. Menu links (id="menu-section")
- 3 links: Brunch / Dinner / Drinks, Genos 48px desktop / 40px mobile, uppercase, underlined, color `#263264` desktop / `#041E42` mobile. Each opens a PDF in a new tab: `assets/menus/brunch.pdf`, `dinner.pdf`, `drinks.pdf` (paths are tweakable/config values — see Design Tokens).
- "Menu" label: Freehand cursive 49px desktop / 40px mobile, color `#f16f2f`, slight rotation on mobile.
- "MAKE A RESERVATION" button (filled variant): navy `#041E42` bg, `#F0EDD1` text, no border, Geist Mono, bold, 16px, letter-spacing 1.5px, padding 16px 28px. Hover: bg becomes `#C0E0F2`, text `#041E42`. Click → `tel:+355674050776`.

### 7. Aperitivo marquee (bg `#041E42`)
- Same infinite-scroll technique as Brunch marquee, using a single wide illustration asset (fish + "Aperitivo" text SVG, `pasted-...svg` in assets) instead of individual items. Desktop height ~206px with 56px top/bottom padding; mobile compressed to fit ~65px height, image scaled to 287×45px (proportional to viewport).
- Two of the aperitivo icon illustrations (fish shapes) are rotated 90° via `filter: brightness(0) invert(1)` (turns navy line art white) + `transform: rotate(90deg)`.

### 8. Aperitivo gallery
- Same carousel pattern as Brunch gallery (desktop: full row of photos; mobile: 2-visible carousel with same arrow controls), bg `#263264`.

### 9. Footer (id="contact-section", bg `#041E42`)
- Logo: `assets/sora-logo.svg`, large, centered (1160×205px desktop / 320×57px mobile).
- 4 columns (desktop grid, mobile stacked): Address, Contact, Hours, Follow Us.
  - Address: "Plazh, Durrës · Albania ↗" — links to Google Maps: `https://maps.app.goo.gl/JDuTTC6TZMxkr7fR9` (opens native Maps app on mobile, Maps web on desktop).
  - Contact: "+355 67 405 0776" as a `tel:+355674050776` link (dials on mobile).
  - Hours: "07:00 - 01:00".
  - Follow Us: "Instagram" linking to `https://www.instagram.com/sora.brunch.aperitivo/`.
  - Column heading style: Inter 600, 24px desktop / 20px mobile, letter-spacing 3.84px, uppercase, color `#f0edd1`. Body: Inter 500 (desktop) or Cousine (mobile), 14px, color `#f0edd1`.

### 10. Scroll-to-top button
- Fixed bottom-right (24px from edges), 48px circle, `rgba(255,255,255,0.5)` bg, `#F0EDD1` up-arrow icon (simple chevron/arrow SVG stroke). Appears only after scrolling past 200px (opacity/visibility toggle). Hover: 1.5px `#F0EDD1` border/stroke appears around the circle.

## Interactions & Behavior
- Nav click → smooth-scrolls to the matching section id (`about-section`, `gallery-section`, `menu-section`, `contact-section`), sets that item as "active" (color changes to `#F0EDD1` until another is clicked).
- Reservation buttons (3 total: header, mobile menu, menu section) all trigger `window.location.href = "tel:+355674050776"`.
- Carousels (Brunch + Aperitivo galleries, mobile only): tap-driven, one-image-at-a-time slide, arrows conditionally rendered based on scroll position.
- Scroll-triggered animations (About text reveal, cocktail shake) each fire once via IntersectionObserver at ~20% visibility threshold, no replay on scroll back up.
- Responsive breakpoint: <768px = mobile layout (entirely different markup/positioning, not just reflowed), ≥768px = desktop layout that scales as a unit between 1440px (100%) and 1920px (max).

## State Management
- `activeNav`: which nav item is highlighted (string: "about" | "gallery" | "menu" | "contact").
- `mobileMenuOpen`: boolean, hamburger dropdown visibility.
- `scrolled`: boolean, drives scroll-to-top button visibility (scrollY > 200).
- `brunchOffset` / `aperitivoOffset`: integer carousel position (0 to images.length - 2), drives `translateX(-offset*50%)`.
- `visible.{name}`: per-animated-element boolean set once by IntersectionObserver, drives the word-reveal and cocktail-shake animations.
- Viewport width tracked via resize listener to switch mobile/desktop layout and compute the scale factor.

## Design Tokens
**Colors**
- Navy (primary dark): `#041E42`
- Cream (primary light bg): `#F0EDD1`
- Sky blue (accent/stroke): `#C0E0F2`
- Orange (accent, "Menu"/"The hour" labels): `#F16F2F`
- Deep blue (secondary bg, About headings): `#263264` / `#15316d` (brunch marquee text) / `#c0e0f2` (aperitivo marquee text)
- Body text gray: `#474747`
- White at 50% opacity: `rgba(255,255,255,0.5)` (default nav state, carousel arrow bg)

**Typography** (Google Fonts)
- Freehand (cursive) — decorative labels ("Brunch", "Aperitivo", "Menu", hero times)
- Genos — large display headings
- Geist (600) — "ABOUT" nav label
- Geist Mono (500/600/700) — nav labels, body copy, buttons
- Inter (500/600) — footer headings/body
- Cousine — footer body (mobile), address link

**Spacing/Scale**
- Desktop canvas: 1440px base, scales up to 1920px max via `scale()` transform (not fluid reflow).
- Mobile canvas: 375px base, scales fluidly with viewport width.
- Marquee loop: 22s linear infinite, track doubled for seamless wrap.

**Border radius**: 0px on buttons (explicitly square). Hero circles use 400px (desktop) / 187.5px (mobile) radius on two corners only (half-circle effect).

## Assets
All in `assets/` (copied into this handoff folder):
- `sora-logo.svg` — logo, color `#F0EDD1`
- `hero-arch.png` / `hero-arch-sm.jpg` — hero archway photo
- `shopfront-illustration.svg`, `cocktail-illustration.svg` — line-art illustrations
- `the-hour.svg` — flattened "The ° hour" text as vector (intentionally not live text, to avoid reflow issues)
- `brunch-icon-a/b/c/d.svg` — brunch marquee icons
- `aperitivo-icon-a/b/c.svg` — aperitivo marquee icons (fish shapes)
- `about-1..4.jpg`, `brunch-photo-1..6.jpg`, `aperitivo-gallery-1..4.jpg` — photography
- `menus/brunch.pdf`, `menus/dinner.pdf`, `menus/drinks.pdf` — menu PDFs (opened via links, replaceable independently)
- `arch_text-*.svg` — small rotated "sunrise/sunset" arch text graphic in the About collage
- `pasted-1785336853683-0-*.svg` — wide Aperitivo marquee illustration (fish + text combined)

## Files
- `SORA Landing Page.dc.html` — the full design reference (desktop + mobile in one file, gated by a JS-computed `isMobile`/`isDesktop` flag at the 768px breakpoint).
