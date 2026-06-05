# Landing Page — Design System Override
> Inherits all rules from MASTER.md. Only listed overrides apply.

## Page: `code.html` (főoldal / landing)

### Structure
```
Nav (fixed)
└── Section #home     — Hero, full-viewport
└── Section #menu     — Bento grid, kínálat
└── Section #about    — Rólunk, kép + szöveg
└── Footer #contact   — Kapcsolat, nyitvatartás, social
```

### Section-Specific Notes

**Hero (#home)**
- Background: full-bleed photo + `hero-overlay` gradient
- Logo centered, `w-28 md:w-40`, `rounded-full`
- H1: `display-lg-mobile md:display-lg`, `text-surface`
- CTA: primary button, `px-10 py-4`
- Scroll hint: `fade-pulse` animation, `aria-hidden`
- Hero image: `fetchpriority="high" loading="eager"`

**Kínálatunk (#menu)**
- Grid: `md:grid-cols-12`
  - Large card: `md:col-span-8` — `aspect-[16/9]`
  - Coffee card: `md:col-span-4` — `bg-primary` dark card
  - 3 small cards: `md:col-span-4` each — `aspect-square`
- All product cards: `<article class="product-card group">`
- Price list: `<dl>` with `<dt>`/`<dd>` pairs

**Rólunk (#about)**
- Layout: `flex-col md:flex-row gap-xl`
- Image: `aspect-[4/5]`, offset border frame (`hidden md:block`)
- Stats: `<dl>` with 3 items separated by `w-px bg-outline-variant`
- Section heading: `aria-labelledby="about-heading"`

**Footer (#contact)**
- Background: `bg-primary`
- Text: `text-secondary-fixed` headings, `text-on-primary/70` body
- Grid: `md:grid-cols-3`
- Social: inline SVG (Facebook, Instagram, TikTok) + `rel="noopener noreferrer" target="_blank"`
- Links: real paths (`/impresszum`, `/adatvedelem`, `/karrier`, `/rendezveny`)

### Active Nav State (JS)
```js
IntersectionObserver threshold: 0.4
Active: text-secondary + font-semibold
Inactive: text-on-surface-variant
```
