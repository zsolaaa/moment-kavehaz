---
name: Moment Kávéház Design System
colors:
  surface: '#fff8f6'
  surface-dim: '#fbd1c4'
  surface-bright: '#fff8f6'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#fff1ed'
  surface-container: '#ffe9e3'
  surface-container-high: '#ffe2da'
  surface-container-highest: '#ffdbd0'
  on-surface: '#2c160e'
  on-surface-variant: '#504442'
  inverse-surface: '#442a22'
  inverse-on-surface: '#ffede8'
  outline: '#827472'
  outline-variant: '#d3c3c0'
  surface-tint: '#745853'
  primary: '#271310'
  on-primary: '#ffffff'
  primary-container: '#3e2723'
  on-primary-container: '#ae8d87'
  inverse-primary: '#e3beb8'
  secondary: '#775a19'
  on-secondary: '#ffffff'
  secondary-container: '#fed488'
  on-secondary-container: '#785a1a'
  tertiary: '#191914'
  on-tertiary: '#ffffff'
  tertiary-container: '#2e2d28'
  on-tertiary-container: '#97948d'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#ffdad4'
  primary-fixed-dim: '#e3beb8'
  on-primary-fixed: '#2b1613'
  on-primary-fixed-variant: '#5b403c'
  secondary-fixed: '#ffdea5'
  secondary-fixed-dim: '#e9c176'
  on-secondary-fixed: '#261900'
  on-secondary-fixed-variant: '#5d4201'
  tertiary-fixed: '#e6e2da'
  tertiary-fixed-dim: '#c9c6bf'
  on-tertiary-fixed: '#1c1c17'
  on-tertiary-fixed-variant: '#484741'
  background: '#fff8f6'
  on-background: '#2c160e'
  surface-variant: '#ffdbd0'
typography:
  display-lg:
    fontFamily: Playfair Display
    fontSize: 48px
    fontWeight: '700'
    lineHeight: 56px
    letterSpacing: -0.02em
  display-lg-mobile:
    fontFamily: Playfair Display
    fontSize: 36px
    fontWeight: '700'
    lineHeight: 44px
  headline-md:
    fontFamily: Playfair Display
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
  headline-sm:
    fontFamily: Playfair Display
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  body-lg:
    fontFamily: Work Sans
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Work Sans
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  label-md:
    fontFamily: Work Sans
    fontSize: 14px
    fontWeight: '600'
    lineHeight: 20px
    letterSpacing: 0.05em
rounded:
  sm: 0.125rem
  DEFAULT: 0.25rem
  md: 0.375rem
  lg: 0.5rem
  xl: 0.75rem
  full: 9999px
spacing:
  base: 8px
  xs: 4px
  sm: 12px
  md: 24px
  lg: 48px
  xl: 80px
  gutter: 24px
  margin-mobile: 16px
  margin-desktop: 64px
---

## Brand & Style

This design system embodies the atmosphere of a classic European "Grand Café," blending traditional elegance with contemporary premium service. The visual narrative focuses on the ritual of coffee and the artistry of fine pastry (Chocolatier). 

The chosen style is **Corporate / Modern** with **Tactile** influences. It avoids the coldness of pure minimalism by incorporating rich textures, subtle decorative flourishes inspired by the logo's filigree, and a warm, high-contrast color palette. The UI should evoke a sense of timelessness, indulgence, and professional hospitality.

**Design Principles:**
- **Refined Craftsmanship:** Every border, icon, and transition should feel as intentional as a handcrafted dessert.
- **Warmth & Welcome:** Utilize cream and gold tones to create an inviting digital "interior."
- **Clarity & Heritage:** Balance traditional serif typography with high-functioning layouts to ensure the premium experience is accessible.

## Colors

The palette is derived directly from the deep roasted tones of coffee, the golden glint of premium branding, and the creamy textures of pastries.

- **Primary (Deep Espresso):** Used for primary text, headers, and the most prominent structural elements. It provides the "anchor" for the brand.
- **Secondary (Heritage Gold):** Used for highlights, call-to-action buttons, decorative accents, and icons. This represents the premium quality and the "Moment" sparkle.
- **Tertiary (Clotted Cream):** The primary background color. It is softer and more sophisticated than pure white, echoing the interior walls of the café.
- **Neutral (Cocoa Dust):** Used for secondary text, borders, and subtle UI elements to maintain a monochromatic harmony with the primary brown.

## Typography

The typography strategy relies on the contrast between the authoritative, literary feel of **Playfair Display** and the clean, functional efficiency of **Work Sans**.

- **Headlines:** Always use Playfair Display. For large display titles, use a slightly tighter letter-spacing to emphasize the elegance of the serif strokes.
- **Body Text:** Work Sans provides excellent legibility for menus and descriptions. Its neutral character allows the photography of the desserts to remain the focal point.
- **Labels:** Small labels and "Chocolatier" sub-headers should use Work Sans with increased letter-spacing and uppercase styling to evoke a luxury tag or packaging feel.

## Layout & Spacing

The layout follows a **Fixed Grid** philosophy for desktop to maintain a boutique, curated feel, while transitioning to a fluid model for mobile.

- **Desktop:** 12-column grid with a maximum container width of 1200px. Large 80px vertical margins are used between sections to create "breathing room" and a sense of luxury.
- **Mobile:** 4-column fluid grid. Gutters are reduced to 16px to maximize space for high-resolution imagery.
- **Rhythm:** An 8px base unit governs all spacing. Use "lg" (48px) spacing to separate distinct content blocks (e.g., the story vs. the menu).

## Elevation & Depth

To match the physical environment of the café, depth is conveyed through **Tonal Layers** and **Ambient Shadows**.

- **Surfaces:** Use the Tertiary (Cream) as the base layer. "Floating" elements like cards or modals should use a slightly lighter version of the cream or pure white to pull forward.
- **Shadows:** Avoid harsh black shadows. Use a soft, diffused shadow tinted with the Primary brown (`rgba(62, 39, 35, 0.08)`) with a high blur radius (16px - 24px). This creates a "soft lighting" effect, similar to the warm lamps seen in the interior photos.
- **Outlines:** Use thin (1px) borders in the Secondary Gold for interactive elements to signify their importance without adding visual bulk.

## Shapes

The shape language is **Soft (0.25rem)**. While the logo features elegant curves, the UI remains structured and professional.

- **Corner Radius:** Standard buttons and cards use a subtle 4px radius. This provides a "finished" look without appearing too "bubbly" or casual.
- **Decorative Elements:** The curved filigree from the logo should be used sparingly as background watermarks or section dividers.
- **Imagery:** Photos of the pastries and interior should remain sharp-cornered or use the standard 4px radius to feel like framed art.

## Components

### Buttons
- **Primary:** Solid Heritage Gold (#C5A059) with Espresso text. High-contrast and clear.
- **Secondary:** Espresso border (1px) with Espresso text. Used for less urgent actions.
- **Style:** All-caps label font for a premium "tag" feel.

### Cards
- **Product Cards:** Cream background with a 1px Cocoa Dust border. The product name uses Playfair Display, while price/weight uses Work Sans.
- **Image Treatment:** Use a slight zoom-on-hover effect to give a tactile feel to the pastry photography.

### Inputs & Selection
- **Input Fields:** Bottom-border only style in Cocoa Dust to maintain a "stationary" feel. 
- **Checkboxes/Radios:** Use the Heritage Gold for the active state.

### Specialized Components
- **The "Moment" Divider:** A horizontal line with a small decorative flourish or the "MD" icon in the center to separate menu categories.
- **Menu Lists:** Left-aligned item name in Playfair Display, a dotted leader line, and right-aligned price.