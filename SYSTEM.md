# Moment Kávéház — Project System File

> Single source of truth for all design, code, and content decisions.
> Every contributor (human or AI) reads this file before touching the project.

---

## 1. Project Identity

| Field | Value |
|-------|-------|
| **Project name** | Moment Kávéház |
| **Type** | Landing page — single-page HTML |
| **Stack** | Vanilla HTML · Tailwind CSS (CDN) · Vanilla JS |
| **Fonts** | Playfair Display · Work Sans (Google Fonts) |
| **Icons** | Material Symbols Outlined (Google) |
| **Primary file** | `code.html` |
| **Design reference** | `DESIGN.md` |
| **Language** | Hungarian (hu) |

---

## 2. Brand Essence

**Moment Kávéház** is a classic European grand café with premium pastry (cukrászat). The brand voice is warm, elegant, and timeless — like stepping into a Viennese kávéház in Budapest. Every pixel should convey:

- **Refined Craftsmanship** — intentional, handcrafted feel
- **Warmth & Welcome** — cream and gold create a digital interior
- **Clarity & Heritage** — serif tradition meets modern clarity

---

## 3. Color System

All colors come from Material You tonal palette seeded from deep espresso brown.

### Semantic Tokens

| Token | Hex | Usage |
|-------|-----|-------|
| `primary` | `#271310` | Primary text, section headings, nav |
| `on-primary` | `#ffffff` | Text on primary buttons |
| `primary-container` | `#3e2723` | Dark card backgrounds |
| `secondary` | `#775a19` | Heritage Gold — CTAs, highlights, accents |
| `secondary-container` | `#fed488` | Gold chip/badge backgrounds |
| `on-secondary-container` | `#785a1a` | Text on gold chips |
| `surface` | `#fff8f6` | Page background (cream) |
| `surface-container-low` | `#fff1ed` | Card background |
| `surface-container` | `#ffe9e3` | Hover state backgrounds |
| `surface-container-high` | `#ffe2da` | Active / selected backgrounds |
| `on-surface` | `#2c160e` | Body text, icons on light surfaces |
| `on-surface-variant` | `#504442` | Secondary text, captions |
| `outline` | `#827472` | Borders, dividers |
| `outline-variant` | `#d3c3c0` | Subtle dividers, input borders |
| `error` | `#ba1a1a` | Error states |
| `background` | `#fff8f6` | Same as surface |

### Usage Rules
- Never use raw hex in components — always use the Tailwind token class (e.g. `bg-surface-container`, `text-on-surface`)
- Heritage Gold (`secondary`) is the only true "color" — use it sparingly for CTAs and key accents
- Backgrounds stay in the cream-to-blush range; no pure white sections

---

## 4. Typography

### Type Scale

| Role | Family | Size | Weight | Line-height | Letter-spacing |
|------|--------|------|--------|-------------|----------------|
| Display (desktop) | Playfair Display | 48px | 700 | 56px | −0.02em |
| Display (mobile) | Playfair Display | 36px | 700 | 44px | — |
| Headline MD | Playfair Display | 32px | 600 | 40px | — |
| Headline SM | Playfair Display | 24px | 600 | 32px | — |
| Body LG | Work Sans | 18px | 400 | 28px | — |
| Body MD | Work Sans | 16px | 400 | 24px | — |
| Label MD | Work Sans | 14px | 600 | 20px | +0.05em |

### Rules
- **Headings:** always Playfair Display — never Work Sans for h1–h3
- **Body / labels / nav:** always Work Sans
- **All-caps labels** use Work Sans 600, `letter-spacing: 0.05em` — "luxury tag" feel
- Minimum body size: **16px** (prevents iOS auto-zoom)
- Maximum line length: **65–75 chars** on desktop

---

## 5. Spacing & Layout

### Spacing Scale (8px base)

| Token | Value | Use |
|-------|-------|-----|
| `xs` | 4px | Micro gaps, icon padding |
| `sm` | 12px | Inline element spacing |
| `base` | 8px | Base unit |
| `md` | 24px | Card internal padding, gutter |
| `lg` | 48px | Between content blocks |
| `xl` | 80px | Between major page sections |
| `gutter` | 24px | Column gutter |
| `margin-mobile` | 16px | Horizontal page margin on mobile |
| `margin-desktop` | 64px | Horizontal page margin on desktop |

### Grid
- **Desktop:** 12-column, max container `1200px`, gutter `24px`
- **Mobile:** 4-column fluid, margin `16px`
- **Breakpoints:** 375 / 768 / 1024 / 1440px

---

## 6. Elevation & Depth

- **Base layer:** `surface` (#fff8f6) cream
- **Cards / floating elements:** `surface-container-low` or pure white
- **Shadows:** soft, warm-tinted — `rgba(62, 39, 35, 0.08)` with 16–24px blur (no cold gray shadows)
- **Interactive borders:** 1px `secondary` (Heritage Gold) for focused/hovered interactive elements
- No harsh drop shadows — ambient soft lighting aesthetic only

---

## 7. Shape Language

| Token | Value | Use |
|-------|-------|-----|
| Default | 2px (0.125rem) | Most UI elements |
| `lg` | 4px (0.25rem) | Cards, buttons |
| `xl` | 8px (0.5rem) | Modals, large containers |
| `full` | 12px (0.75rem) | Pills, badges |

- Buttons and cards: `rounded-lg` (4px) — professional, not bubbly
- Photography: sharp corners or `rounded-lg` — feels like framed art
- No large radius (>12px) on structural elements

---

## 8. Component Specs

### Primary Button
```
bg-secondary  text-on-primary  font-work-sans  font-semibold  tracking-widest  uppercase
px-8 py-3  rounded-lg  hover:opacity-90  transition-opacity duration-200
```

### Secondary / Outline Button
```
border border-primary  text-primary  font-work-sans  font-semibold  tracking-widest  uppercase
px-8 py-3  rounded-lg  hover:bg-surface-container  transition-colors duration-200
```

### Product Card
```
bg-surface-container-low  border border-outline-variant  rounded-lg
shadow: 0 4px 16px rgba(62,39,35,0.08)
Image: rounded-lg, zoom-on-hover (scale-105, duration-300)
Title: Playfair Display 20px/600
Price: Work Sans 14px/600 text-on-surface-variant
```

### "Moment" Section Divider
Horizontal `outline-variant` line + centered brand monogram or decorative flourish. Used between menu categories.

### Menu List Item
```
flex justify-between  font-playfair (name)  dotted leader  font-work-sans (price, right-aligned)
```

### Input Field
```
border-b border-outline  bg-transparent  focus:border-secondary
No outer border box — "stationery" feel
```

---

## 9. Motion & Animation

| Property | Value |
|----------|-------|
| Micro-interactions | 150–300ms |
| Page-level transitions | ≤ 400ms |
| Easing (enter) | ease-out |
| Easing (exit) | ease-in |
| Image hover zoom | `scale-105`, 300ms ease-out |
| Respect `prefers-reduced-motion` | Yes — disable all transforms/transitions |

- Animate with `transform` and `opacity` only (no width/height/top/left)
- Max 1–2 animated elements per viewport at once
- No decorative-only animations

---

## 10. Accessibility Checklist

- [ ] Contrast ≥ 4.5:1 for body text (`on-surface` on `surface` = ✓)
- [ ] All images have descriptive `alt` text
- [ ] All icon-only buttons have `aria-label`
- [ ] Focus rings visible (2px solid `secondary`)
- [ ] Tab order matches visual order
- [ ] `lang="hu"` on `<html>`
- [ ] Viewport meta never disables zoom
- [ ] `prefers-reduced-motion` media query handled

---

## 11. File Structure

```
MomentKávéház/
├── SYSTEM.md          ← this file (source of truth)
├── DESIGN.md          ← extended design rationale + color tokens (YAML frontmatter)
├── code.html          ← production landing page
├── logo.jpg           ← brand logo
├── screen.png         ← landing page screenshot reference
├── *.jpg              ← product / interior photography
└── stitch_moment_*.zip ← archived version
```

---

## 12. Content Tone

- **Language:** Hungarian — formal but warm (`Önök` forms acceptable, but `te/ti` is fine for younger audience)
- **Tagline territory:** moments, craft, ritual, indulgence, artistry
- **Avoid:** corporate jargon, hyperbolic superlatives, emoji in UI text
- **Photo captions:** short, poetic — focus on sensory experience

---

## 13. Anti-Patterns (Never Do)

| Anti-pattern | Reason |
|---|---|
| Raw hex in Tailwind classes | Breaks token system — use semantic token names |
| Emoji as navigation icons | Inconsistent cross-platform, not themeable |
| Pure white (#ffffff) background sections | Breaks the warm cream aesthetic |
| Mixing Playfair + Work Sans for the same role | Destroys typographic hierarchy |
| Cold gray shadows | Clashes with warm brand palette |
| Rounded corners > 12px on cards/buttons | Too playful, loses premium feel |
| Horizontal scroll on mobile | UX failure |
| Animations > 400ms without user trigger | Feels slow and bloated |
| Text < 16px on body | Triggers iOS auto-zoom |

---

## 14. Quick Dev Reference

```html
<!-- Tailwind CDN with plugins -->
<script src="https://cdn.tailwindcss.com?plugins=forms,container-queries"></script>

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600;700&family=Work+Sans:wght@400;500;600&display=swap" rel="stylesheet"/>

<!-- Material Icons -->
<link href="https://fonts.googleapis.com/css2?family=Material+Symbols+Outlined:wght,FILL@100..700,0..1&display=swap" rel="stylesheet"/>
```

**Font utility classes (custom Tailwind config):**
```js
fontFamily: {
  'playfair': ['Playfair Display', 'Georgia', 'serif'],
  'work': ['Work Sans', 'system-ui', 'sans-serif']
}
```

---

*Last updated: 2026-06-05*
