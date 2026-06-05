# Moment Kávéház — Design System MASTER
> Global Source of Truth. All pages inherit these rules unless a page-specific override in `pages/` says otherwise.
> Generated from: DESIGN.md + SYSTEM.md + UI/UX Pro Max analysis
> Last updated: 2026-06-05

---

## 1. Product Profile

| Field | Value |
|---|---|
| **Project** | Moment Kávéház |
| **Type** | Brand landing page (single-page HTML) |
| **Industry** | Café / Premium pastry / Hospitality |
| **Register** | Brand (design IS the product) |
| **Style family** | Corporate-Tactile / Warm Premium |
| **Color strategy** | Committed — Heritage Gold carries 30–40% of accents |
| **Primary audience** | Adult Budapesti foodies, 25–55, leisure intent |
| **Anti-references** | Generic SaaS cream, pure minimalism, cold neutrals |

---

## 2. Color System

All tokens follow Material You tonal palette seeded from deep espresso `#271310`.

### Core Semantic Tokens

| Token | Hex | Role |
|---|---|---|
| `primary` | `#271310` | Text anchors, headings, nav, footer bg |
| `on-primary` | `#ffffff` | Text/icons on primary bg |
| `primary-container` | `#3e2723` | Dark card bg, coffee section |
| `on-primary-container` | `#ae8d87` | Secondary text on dark card |
| `secondary` | `#775a19` | Heritage Gold — CTAs, accents, dividers, active nav |
| `on-secondary` | `#ffffff` | Text on gold buttons |
| `secondary-container` | `#fed488` | Gold chip/badge bg |
| `secondary-fixed` | `#ffdea5` | Light gold for footer on dark bg |
| `surface` | `#fff8f6` | Page bg (warm cream) |
| `surface-container-low` | `#fff1ed` | Card bg |
| `surface-container` | `#ffe9e3` | Hover state bg |
| `surface-container-high` | `#ffe2da` | Active/selected bg |
| `on-surface` | `#2c160e` | Body text, icons on light bg |
| `on-surface-variant` | `#504442` | Secondary text, captions |
| `outline` | `#827472` | Borders |
| `outline-variant` | `#d3c3c0` | Subtle dividers, input borders |
| `error` | `#ba1a1a` | Error states |

### Rules
- Never use raw hex in components — always use Tailwind token class
- `secondary` (Heritage Gold) is the only saturated accent — use sparingly
- Background always warm cream; no pure white sections
- Shadows: `rgba(39,19,16,0.08–0.12)` warm-tinted, high blur (16–24px)

---

## 3. Typography

### Font Stack

| Role | Family | Fallback |
|---|---|---|
| Headings (h1–h3) | Playfair Display | Georgia, serif |
| Body / UI | Work Sans | system-ui, sans-serif |

### Type Scale

| Token | Family | Size | Weight | Line-height | Letter-spacing |
|---|---|---|---|---|---|
| `display-lg` | Playfair Display | 48px | 700 | 56px | −0.02em |
| `display-lg-mobile` | Playfair Display | 36px | 700 | 44px | — |
| `headline-md` | Playfair Display | 32px | 600 | 40px | — |
| `headline-sm` | Playfair Display | 24px | 600 | 32px | — |
| `body-lg` | Work Sans | 18px | 400 | 28px | — |
| `body-md` | Work Sans | 16px | 400 | 24px | — |
| `label-md` | Work Sans | 14px | 600 | 20px | +0.05em |

### Rules
- h1–h3: always Playfair Display
- Body / nav / labels: always Work Sans
- All-caps labels: Work Sans 600, `letter-spacing: 0.05em`
- Min body: **16px** (prevents iOS auto-zoom)
- Max line length: **65–75ch** desktop

---

## 4. Spacing Scale

Base unit: **8px**

| Token | Value | Use |
|---|---|---|
| `xs` | 4px | Micro gaps |
| `sm` | 12px | Inline spacing |
| `base` | 8px | Base unit |
| `md` | 24px | Card padding, gutter |
| `lg` | 48px | Between content blocks |
| `xl` | 80px | Between page sections |
| `gutter` | 24px | Column gutter |
| `margin-mobile` | 16px | Page edge mobile |
| `margin-desktop` | 64px | Page edge desktop |

---

## 5. Layout

- **Grid:** 12-col, `max-w-[1200px]`, `gap-gutter`
- **Mobile:** fluid, `px-margin-mobile`
- **Desktop:** `px-margin-desktop`
- **Breakpoints:** 375 / 768 / 1024 / 1440px
- **Viewport:** `min-h-dvh` (not `h-screen`)
- **Scroll:** `scroll-behavior: smooth` inside `prefers-reduced-motion: no-preference`

---

## 6. Shape Language

| Token | Value | Use |
|---|---|---|
| Default | 2px | Most elements |
| `rounded-lg` | 4px | Cards, buttons |
| `rounded-xl` | 8px | Modals, large containers |
| `rounded-full` | 12px | Pills, badges, logo circles |

- No radius > 12px on structural elements

---

## 7. Elevation & Shadow

- Base layer: `surface` cream
- Cards/floating: `surface-container-low` or `#ffffff`
- Shadow formula: `0 4px 16px rgba(39,19,16,0.08)` → `0 20px 40px rgba(39,19,16,0.12)` on hover
- No cold gray shadows

---

## 8. Motion

| Property | Value |
|---|---|
| Micro-interactions | 150–300ms |
| Complex transitions | ≤ 400ms |
| Enter easing | ease-out |
| Exit easing | ease-in |
| Image hover zoom | `scale-105`, 700ms ease-out |
| Card lift | `translateY(-4px)`, 300ms ease-out |
| Mobile menu | `grid-template-rows: 0fr → 1fr`, 300ms ease-out |
| Scroll hint | `fade-pulse` keyframe — opacity + translateY only |

- **Only animate:** `transform`, `opacity`, `box-shadow`
- **Never animate:** `width`, `height`, `max-height`, `top`, `left`
- `prefers-reduced-motion: reduce` → disable all transforms and animations

---

## 9. Component Specs

### Primary Button
```
bg-secondary text-on-secondary
px-10 py-4 (large) / px-6 py-2 (small)
font-label-md uppercase tracking-widest
rounded-lg
hover:opacity-90 transition-opacity
active:scale-95
```

### Secondary / Outline Button
```
border border-primary text-primary
Same padding as primary
hover:bg-surface-container transition-colors
```

### Product Card (`<article>`)
```
bg-surface-container-low rounded-lg
CSS class: .product-card
  transition: transform 0.3s ease-out, box-shadow 0.3s ease-out
  hover: translateY(-4px), shadow 0 20px 40px rgba(39,19,16,0.12)
Image: rounded-t-lg, group-hover:scale-105 duration-700
Title: font-display-lg text-headline-sm
Description: font-body-md text-on-surface-variant
```

### Menu Price List (`<dl>`)
```
dt: font-label-md (item name, left)
dd: font-label-md (price, right)
Row: flex justify-between, border-b border-secondary/30 pb-2 mb-2
```

### Section Divider
```html
<div class="moment-divider" role="presentation">
  <span aria-hidden="true" class="absolute top-1/2 left-1/2 -translate-x-1/2 -translate-y-1/2 bg-surface px-2 text-secondary text-xs">✦</span>
</div>
```
CSS: `height: 1px; background: secondary; max-width: 120px; margin: 0 auto;`

### Stat Block (`<dl>`)
```
dd: font-display-lg text-headline-sm text-secondary (value, order-1)
dt: font-label-md uppercase text-on-surface-variant (label, order-2)
Separator: w-px h-12 bg-outline-variant (aria-hidden)
```

### Navigation (Desktop)
```html
<ul class="hidden md:flex gap-md items-center list-none">
  <li><a href="#section">…</a></li>
</ul>
```
Active state: `text-secondary font-semibold` (JS scroll observer)

### Mobile Menu
```css
#mobile-menu {
  display: grid;
  grid-template-rows: 0fr;  /* closed */
  opacity: 0;
  transition: grid-template-rows 0.3s ease-out, opacity 0.25s ease-out;
}
#mobile-menu.open { grid-template-rows: 1fr; opacity: 1; }
#mobile-menu > div { overflow: hidden; }
```

---

## 10. Accessibility Baseline

- `:focus-visible` — `outline: 2px solid #775a19; outline-offset: 2px`
- Skip-to-content link before `<nav>`
- `<main id="main-content">` wraps all page content
- `<section>` for content areas (not `<header>`)
- `<article>` for product cards
- `<nav>` with `aria-label` for each nav landmark
- `<ul>/<li>` for nav lists (no `role="list"` on divs)
- `<dl>/<dt>/<dd>` for price lists and stats
- `<address>` for contact info
- `aria-expanded` + `aria-controls` on hamburger `<button>`
- `aria-hidden="true"` on decorative icons and separators
- `lang="hu"` on `<html>`
- `fetchpriority="high" loading="eager"` on hero image
- `loading="lazy" width height` on all below-fold images
- `prefers-reduced-motion` handled for all animations

---

## 11. Performance Baseline

- Hero image: `fetchpriority="high" loading="eager"`
- All other images: `loading="lazy"` + explicit `width`/`height`
- Google Fonts: single `<link>` (no duplicates)
- `scroll-behavior: smooth` only inside `@media (prefers-reduced-motion: no-preference)`
- No `transition-all` — always explicit properties
- No `max-height` animation — use `grid-template-rows` trick

---

## 12. SEO & Meta Minimum

```html
<meta name="description" content="…"/>
<meta property="og:title" content="…"/>
<meta property="og:description" content="…"/>
<meta property="og:type" content="website"/>
<meta property="og:locale" content="hu_HU"/>
```

---

## 13. Anti-Patterns

| Forbidden | Reason |
|---|---|
| Raw hex in Tailwind classes | Breaks token system |
| `transition-all` | Animates layout properties |
| `max-height` animation | Layout thrash |
| `h-screen` on hero | iOS Safari viewport bug |
| `href="#"` placeholder links | Scrolls to top, breaks UX |
| `role="list"` on div | Screen reader ignores it |
| `cursor-pointer` on `<a>` | Browser default, redundant |
| Emoji as icons | Cross-platform inconsistent |
| Pure white `#ffffff` background sections | Breaks warm brand palette |
| Cold gray shadows | Clashes with warm palette |
| Headings in Work Sans | Typography hierarchy violation |
| Body text in Playfair | Readability failure |
| Bounce animation (`animate-bounce`) | AI slop telltale sign |
| `content: '✦'` in CSS pseudo-element | Screen readers may read it |
| Nested `<nav>` with `role="navigation"` on inner div | Redundant landmark |

---

## 14. Copy Guidelines

- Language: Hungarian (`hu`)
- Tone: warm, poetic, sensory — "selymes", "harmonikus", "pillanat"
- No em dashes — use colon, comma, or period
- No corporate jargon, no superlatives
- Photo captions: short, sensory

---

## 15. File Structure

```
MomentKávéház/
├── design-system/
│   ├── MASTER.md          ← this file
│   └── pages/             ← page-specific overrides (empty = use Master)
├── SYSTEM.md              ← project overview + quick dev reference
├── DESIGN.md              ← extended rationale + color YAML frontmatter
├── code.html              ← production landing page
├── logo.jpg
├── screen.png
└── *.jpg                  ← product photography
```

---

## How to Use This File

**When building or editing any page:**

1. Read this file first
2. Check `design-system/pages/<page-name>.md` for overrides
3. If no page file exists, Master rules apply exclusively
4. Never deviate from token names, spacing scale, or anti-pattern list without updating this file

**Retrieval prompt template:**
```
I am building the [Page Name] page for Moment Kávéház.
Read design-system/MASTER.md.
Check if design-system/pages/[page-name].md exists — if so, its rules override Master.
Now generate the code following those rules.
```
